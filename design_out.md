Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario: Kobalos Malware Investigation**

**INFO_LEVEL:**
- The target network has been compromised by the Kobalos malware, a sophisticated Linux backdoor targeting high-performance computing clusters.
- Your task is to investigate the compromise, identify indicators of compromise (IOCs), and contain the threat.
- The malware is known to grant remote access, steal SSH credentials, and exfiltrate data.

**ACCESS_LEVEL:**
- Entry host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate the suspicious service running on the target host.
**Description:**
- The target host is exhibiting unusual network activity. Investigate the running services and identify any suspicious activity.
- Look for services that should not be running or those that are consuming unusual amounts of resources.
**Hint:** Check the systemd services and look for any unfamiliar or recently created services.
**Flag:** payload-transfer.service

**TRAINING_LEVEL 2:**
**Task:** Identify the data exfiltration mechanism.
**Description:**
- The Kobalos malware is known to exfiltrate data. Investigate the network connections and identify any suspicious outbound connections.
- Determine the destination IP address and port used for exfiltration.
**Hint:** Check the network connections and look for any unusual outbound connections.
**Flag:** 192.168.40.5:7070

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication.
**Description:**
- To prevent further data exfiltration, you need to contain the C2 communication.
- Identify the port used for C2 communication and block it using the firewall.
**Hint:** Use iptables to block the identified port.
**Flag:** 7070

---

This scenario is aligned with the provided MISP event, security profile, and sandbox environment. It focuses on investigating the Kobalos malware, identifying IOCs, and containing the threat. The tasks are designed to be realistic and achievable within the given sandbox environment.