### INFO_LEVEL

**Scenario Title:** BRICKSTORM Incident Response Investigation  
**Description:**  
Participants are tasked with investigating a compromised Linux host (`target`) that has been infected with the BRICKSTORM backdoor. The malware exhibits advanced evasion techniques, including DoH, nested TLS encryption, and abuse of legitimate cloud services. It uses SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. The backdoor also implements self-preservation mechanisms through environment variable checks and process reinstallation.

The sandbox environment simulates a post-compromise scenario where an attacker has already established a foothold on the `target` host. The environment includes three machines:

- **target** — the initially compromised host, running a C2 listener and a persistent lateral-movement agent
- **next-target** — a secondary host receiving stolen data via SSH-based file transfer
- **c2-server** — the attacker's command-and-control server, periodically connecting to the target to exfiltrate system inventory

Participants start on the target-side network and must investigate active services, running processes, scheduled tasks, and network connections to reconstruct the attack chain.

**Learning Objectives:**
- Identify persistence mechanisms hidden in systemd services and timers
- Detect active network listeners and outbound C2 connections
- Trace lateral movement via SSH and rsync
- Analyse shell scripts deployed as malware payloads
- Correlate log evidence across multiple hosts

---

### ACCESS_LEVEL

**Access Instructions:**
Participants begin their investigation on the `target` host. The `cyrano` user has sudo privileges on the `target` and `c2-server` hosts.

**Credentials:**
- Username: `cyrano`
- Password: `cyrano`

**Network Access:**
- The `target` and `next-target` hosts are on the `192.168.50.0/24` network.
- The `c2-server` is on the `192.168.40.0/24` network, which is not directly accessible to participants.
- Participants can observe traffic to/from the C2 server only from the `target` side.

**Tools Available:**
- Standard Linux command-line tools (`ps`, `netstat`, `systemctl`, `grep`, `cat`, `ls`, etc.)
- SSH access to `next-target` via passwordless SSH
- Log files located in `/var/log/` and `/home/cyrano/`
- Systemd timers and services
- Network tools (`nc`, `ss`, `nmap`, etc.)

---

### TRAINING_LEVEL

#### Task 1: Identify Suspicious Service Persistence Mechanism  
**Objective:**  
Identify the systemd service responsible for maintaining persistence on the `target` host.

**Instructions:**  
Use `systemctl` to list all running services and timers. Identify which service or timer is responsible for maintaining persistence on the host.

**Hint:**  
Look for services or timers that are enabled and running, and consider which ones might be related to data exfiltration or lateral movement.

**Flag:**  
`payload-transfer.service`

---

#### Task 2: Detect C2 Communication  
**Objective:**  
Detect the presence of a C2 listener on the `target` host and identify the port it is listening on.

**Instructions:**  
Use `ss` or `netstat` to identify listening ports on the `target` host. Confirm that a service is listening on port `8080` and is likely serving as a C2 listener.

**Hint:**  
The C2 listener is a benign service designed to mimic a monitoring endpoint. It is configured to serve the contents of `/var/log/local-inventory/inventory.log` when connected to.

**Flag:**  
`8080`

---

#### Task 3: Trace Lateral Movement  
**Objective:**  
Trace the lateral movement mechanism used by the backdoor to transfer data to the `next-target` host.

**Instructions:**  
Use `systemctl` to identify the service responsible for transferring data to the `next-target` host. Confirm that the service is running and is using SSH to transfer data.

**Hint:**  
The service is configured to run an infinite rsync loop, copying data from `/home/cyrano/` to `next-target:/home/cyrano/`.

**Flag:**  
`payload-transfer.service`