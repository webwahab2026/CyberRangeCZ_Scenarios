Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a PACHA malware infection on Linux servers.

---

**INFO_LEVEL:**
The scenario simulates a network compromised by the PACHA backdoor malware, which is known to infect Linux servers with coinminers. The malware uses iptables rules and downloads additional payloads from various URLs. Your task is to investigate the compromised hosts, identify the malware's persistence mechanisms, and contain the threat.

**ACCESS_LEVEL:**
- Entry host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service used for command and control (C2) communication.
**Description:** The compromised host is communicating with a command and control server. Investigate the running services and identify the suspicious service used for C2 communication.
**Hint:** Check the systemd services and look for any unusual services.
**Flag:** sh.service

**Validation:** The user must submit the correct service name (sh.service) used for C2 communication.

**TRAINING_LEVEL 2:**
**Task:** Investigate the service persistence mechanism.
**Description:** The malware has established persistence on the compromised host. Investigate the service persistence mechanism and identify the service name.
**Hint:** Check the systemd services and look for any unusual services.
**Flag:** sh.service

**Validation:** The user must submit the correct service name (sh.service) used for persistence.

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication by blocking the outbound port.
**Description:** To prevent further communication with the command and control server, you need to block the outbound port used for C2 communication. Identify the port and contain the threat.
**Hint:** Check the listening ports and look for any unusual ports.
**Flag:** 80

**Validation:** The user must submit the correct port number (80) used for C2 communication and block it using iptables.

---

This scenario is designed to be consistent with the provided sandbox environment, MISP event, and security profile. The tasks are aligned with the NICE Incident Response profile and focus on investigating, analyzing, and responding to network cybersecurity incidents. The scenario also follows the training level examples provided, ensuring the tasks are of appropriate style, complexity, and validation.