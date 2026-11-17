Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Name:** Sofacy Fysbis Backdoor Investigation

**Difficulty Level:** Intermediate

**Cybersecurity Approach:** Defense-oriented

**Scenario Type:** Exercise

**Objective:** Investigate and contain the Sofacy Fysbis backdoor on a compromised Linux host.

---

**INFO_LEVEL:**

The target system has been compromised by the Sofacy Fysbis backdoor, a modular Linux trojan/backdoor. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**Entry Point:**
- Hostname: target
- Username: cyrano
- Password: cyrano

**Network Topology:**
- target (192.168.50.5)
- next-target (192.168.50.6)
- c2-server (192.168.40.5)

**Tools Available:**
- Standard Linux command-line tools
- Systemd service manager
- Network investigation tools (ss, tcpdump, etc.)

---

**ACCESS_LEVEL:**

1. SSH into the target host using the provided credentials.
2. Investigate the system for signs of compromise.
3. Identify and contain the malicious activity.

---

**TRAINING_LEVEL 1:**

**Task:** Suspicious C2 Service Discovery

Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**

1. List all systemd services to identify suspicious ones:
   ```
   systemctl list-units --type=service --all
   ```
2. Check the status of the suspicious service (ksysdef.service) to gather more information:
   ```
   systemctl status ksysdef.service
   ```
3. Inspect the service unit file to understand its configuration and behavior:
   ```
   systemctl cat ksysdef.service
   ```
4. The hidden flag is the name of the suspicious service.

**Hints:**
1. Use `systemctl` commands to list and inspect services.
2. Look for services with unusual names or descriptions.
3. The suspicious service is a network-facing component.

---

**TRAINING_LEVEL 2:**

**Task:** C2 Communication Discovery (Port)

An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**

1. Inspect the suspicious service unit file to find the port number:
   ```
   systemctl cat ksysdef.service
   ```
2. Look for the `ExecStart` line, which specifies the command launched by the service with a port number as an argument.
3. The hidden flag is the port number used by the suspicious service.

**Hints:**
1. The port number is specified in the service unit file.
2. Look for the `ExecStart` line in the service configuration.
3. The port number is an argument to the `ncat` command.

---

**TRAINING_LEVEL 3:**

**Task:** C2 Containment

Investigation has identified unauthorized communication involving the compromised host. Apply an appropriate network control to prevent further communication with the suspicious remote system while preserving legitimate network access.

**Step-by-Step Solution:**

1. Identify the relevant network communication using the port number discovered in the previous task:
   ```
   ss -tunap | grep <port_number>
   ```
2. Apply a targeted firewall rule to block incoming connections to the suspicious port:
   ```
   sudo iptables -I INPUT -p tcp --dport <port_number> -j DROP
   ```
3. Verify that the firewall rule has been applied and is blocking the suspicious port:
   ```
   sudo iptables -L -n -v
   ```
4. The hidden flag is the blocked IP address or port, with firewall state validation.

**Hints:**
1. Use `ss` or `netstat` to identify the network communication.
2. Apply a targeted firewall rule to block the suspicious port.
3. Verify the firewall rule using `iptables -L -n -v`.

---

**Validation:**

1. **TRAINING_LEVEL 1:** Verify that the student has identified the correct service name (ksysdef.service).
2. **TRAINING_LEVEL 2:** Verify that the student has identified the correct port number used by the suspicious service.
3. **TRAINING_LEVEL 3:** Verify that the student has applied the correct firewall rule and that the suspicious port is blocked.

---

This scenario is designed to be deployable in the KYPO/CyberRangeCZ platform and strictly aligned with the provided sandbox environment and MISP event. The tasks are structured to guide students through the investigation and containment of the Sofacy Fysbis backdoor while adhering to the security profile and training level examples.