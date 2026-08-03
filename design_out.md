Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Kobalos Malware Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on its high-performance computing (HPC) cluster. Initial analysis suggests a potential compromise by the Kobalos malware, which is known to target HPC systems. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host (192.168.50.5) with the username `cyrano` and password `cyrano`. From this host, you can investigate the compromise and access other systems as needed.

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:** While monitoring network traffic, you noticed unusual outbound connections from the target host (192.168.50.5) to an unknown IP address. Investigate this activity and determine if it's related to the Kobalos malware.
**Hint:** Check the system logs and network connections for suspicious activity.
**Validation:** The task is considered successful if the student identifies the suspicious port (7070) used for the outbound connections.

**TRAINING_LEVEL 2:**
**Task:** Identify Malicious Service
**Description:** During your investigation, you found evidence of a suspicious service running on the target host. Identify this service and determine if it's related to the Kobalos malware.
**Hint:** Look for services that are not part of the standard system configuration.
**Validation:** The task is considered successful if the student identifies the malicious service (OpenSSHserver.service).

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** You suspect that the attacker might be attempting to move laterally within the network. Investigate the target host (192.168.50.5) for any evidence of lateral movement to other systems, specifically the next-target host (192.168.50.6).
**Hint:** Check for any scheduled tasks or services that transfer data to other hosts.
**Validation:** The task is considered successful if the student identifies the payload-transfer.service that is transferring data to the next-target host.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating the Kobalos malware, which is known to target HPC systems and provide remote access, lateral movement capabilities, and data exfiltration. The scenario also aligns with the Incident Response security profile, which involves investigating, analyzing, and responding to network cybersecurity incidents.