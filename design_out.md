Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I'll create a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario will focus on investigating and responding to the BRICKSTORM backdoor malware.

---

**Scenario: BRICKSTORM Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on one of its Linux servers. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**ACCESS_LEVEL:**
- Entry host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Investigate the suspicious service running on the target host.
**Description:** While monitoring the target host, you noticed an unusual service consuming network resources. Investigate this service to determine if it's malicious.
**Hint:** Check the running services and look for any that seem out of place.
**Validation:** The service name is "updatemgr".

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service maintains persistence.
**Description:** Now that you've identified the suspicious service, investigate how it maintains persistence on the system.
**Hint:** Check the systemd services and look for any related to the suspicious service.
**Validation:** The persistence mechanism is related to the "updatemgr.service".

**TRAINING_LEVEL 3:**
**Task:** Identify the network port used for command-and-control (C2) communication.
**Description:** The suspicious service appears to be communicating with an external server. Identify the network port used for this communication.
**Hint:** Check the network connections and look for any related to the suspicious service.
**Validation:** The C2 port number is "4444".

---

This scenario is aligned with the provided MISP event, security profile, and sandbox environment. It focuses on investigating and responding to the BRICKSTORM backdoor malware, with tasks that are consistent with the available hosts, services, and network topology. The tasks are designed to challenge the student's incident response skills while adhering to the constraints and requirements provided.