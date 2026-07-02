Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario: Mirai Botnet Investigation**

**INFO_LEVEL:**
- The network has been experiencing unusual traffic patterns and performance degradation.
- Initial investigations suggest a possible botnet infection.
- Your task is to investigate and contain the threat.

**ACCESS_LEVEL:**
- Entry host: bot1 (IP: 192.168.70.10)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service communicating with the C2 server.
**Description:**
- Investigate the system services on bot1.
- Identify the service responsible for beaconing to the C2 server.
- The service name will be your flag.
**Hint:** Check the systemd services and look for unusual service names.
**Q/A:**
- Q: What is the name of the suspicious beacon service?
- A: bot-beacon-Hilix.x86.elf.service

**TRAINING_LEVEL 2:**
**Task:** Identify the persistence mechanism used by the malware.
**Description:**
- Investigate the systemd timers and services on bot1.
- Identify the persistence mechanism that ensures the malware runs after reboots.
- The service name will be your flag.
**Hint:** Look for services related to system updates or health checks.
**Q/A:**
- Q: What is the name of the persistence service?
- A: system-update-checker.service

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication by blocking the outbound connection to the C2 server.
**Description:**
- Identify the IP address and port used for C2 communication.
- Implement a firewall rule to block this communication.
- The port number will be your flag.
**Hint:** Check the beacon script and the C2 listener configuration.
**Q/A:**
- Q: What is the port number used for C2 communication?
- A: 2222

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating and containing the Mirai botnet infection, which is consistent with the Incident Response security profile. The tasks are designed to be realistic and achievable within the given sandbox environment.