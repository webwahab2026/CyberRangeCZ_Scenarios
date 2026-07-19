# Backdoor Sandbox — KYPO CRP

A KYPO cybersecurity sandbox simulating a Linux backdoor scenario inspired by the **Kobalos** malware. Participants investigate an already-compromised host, discover persistence mechanisms, trace C2 communication, and perform or detect lateral movement to a secondary target.

---

## Scenario Overview

The sandbox presents a realistic post-compromise environment where an attacker has already established a foothold on a Linux host. The environment runs three machines:

- **target** — the initially compromised host, running a C2 listener and a persistent lateral-movement agent
- **next-target** — a secondary host receiving stolen data via SSH-based file transfer
- **c2-server** — the attacker's command-and-control server, periodically connecting to the target to exfiltrate system inventory

Participants start on the target-side network and must investigate active services, running processes, scheduled tasks, and network connections to reconstruct the attack chain.

---

## Network Topology

```
Internet / Management
         |
      [router]
      /       \
server-switch   target-switch
192.168.40.0/24  192.168.50.0/24
     |              |        |
  c2-server      target   next-target
  .40.5          .50.5     .50.6
```

> The `server-switch` network is **not accessible by participants** — they can observe traffic to/from the C2 server only from the target side.

| Host | IP | OS | Role |
|---|---|---|---|
| c2-server | 192.168.40.5 | Ubuntu 24.04 | Attacker C2 |
| target | 192.168.50.5 | Ubuntu 24.04 | Compromised host |
| next-target | 192.168.50.6 | Ubuntu 24.04 | Lateral movement target |

---

## Attack Chain

### 1. Inventory Collection (target)

A systemd timer (`local-inventory.timer`) runs `/usr/local/bin/local-inventory.sh` at boot and every hour thereafter. The script collects:

- Hostname, kernel version, OS, uptime
- Network interfaces and DNS configuration
- Mounted filesystems, disk and memory usage
- Local user accounts

Output is written to `/var/log/local-inventory/inventory.log`.

### 2. C2 Listener (target → c2-server)

`ncat` listens on port **8080** as a systemd service (`lab-checkin-listener.service`). Any client that connects receives the contents of `inventory.log`. This simulates a backdoor exfiltration channel disguised as a monitoring endpoint.

### 3. C2 Check-in (c2-server → target:8080)

A systemd timer on the c2-server (`lab-checkin.timer`) fires every minute. The accompanying script connects to `target:8080`, retrieves the inventory, and appends it to `/home/cyrano/connect_data.log`.

```
c2-server ──[nc]──▶ target:8080 ──▶ inventory.log contents
```

### 4. Lateral Movement (target → next-target)

A persistent systemd service (`payload-transfer.service`) on the target runs an infinite rsync loop, copying `/home/cyrano/` to `cyrano@next-target:/home/cyrano/` every ~5 seconds over passwordless SSH. Host key verification is disabled (`StrictHostKeyChecking=no`).

```
target ──[rsync/SSH]──▶ next-target:/home/cyrano/
```

SSH trust is established at provisioning time via pre-generated ED25519 key pairs and cross-populated `authorized_keys` files.

---

## Users

| Username | Password | Hosts | Privileges |
|---|---|---|---|
| `cyrano` | `cyrano` | target, next-target, c2-server | sudo on target and c2-server |

---

## Persistence Mechanisms Summary

| Mechanism | Service Name | Schedule | Technique |
|---|---|---|---|
| Inventory collection | `local-inventory.timer` | Boot + every 1 hour | Systemd timer (oneshot) |
| C2 listener | `lab-checkin-listener.service` | Always-on | Systemd service, Restart=always |
| C2 check-in | `lab-checkin.timer` | Every 1 minute | Systemd timer (oneshot) |
| Lateral movement | `payload-transfer.service` | Always-on, ~5 s loop | Systemd service, Restart=always |

---

## Provisioning

### Requirements

- Ansible with `community.crypto` collection
- External roles: `user-access`, `disable-qxl`, `sandbox-logging`

Install dependencies:

```bash
ansible-galaxy install -r provisioning/requirements.yml
```

### Running the Playbook

```bash
ansible-playbook provisioning/playbook.yml \
  -e "alice_flag=<flag1>" \
  -e "root_flag=<flag2>" \
  -e "telnet_port=2323"
```

### Role Overview

| Role | Applied To | Description |
|---|---|---|
| `target` | target | User setup, payload files, flags, inventory timer |
| `next-target` | next-target | User setup, flags |
| `ssh_access` | target, next-target | ED25519 key generation, known_hosts, authorized_keys cross-injection |
| `lateral-movement` | target | rsync-over-SSH service to next-target |
| `c2-server` | c2-server | User setup, host aliases |
| `c2-listener` | target | ncat listener on :8080 serving inventory.log |
| `c2-service` | c2-server | Periodic nc check-in client to target:8080 |

---

## Learning Objectives

- Identify persistence mechanisms hidden in systemd services and timers
- Detect active network listeners and outbound C2 connections
- Trace lateral movement via SSH and rsync
- Analyse shell scripts deployed as malware payloads
- Correlate log evidence across multiple hosts


