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
**Description:** During your investigation, you found that a suspicious service is running on the target host. Identify this service and determine its purpose.
**Hint:** Look for services that are not part of the standard system configuration.
**Validation:** The task is considered successful if the student identifies the malicious service (OpenSSH.service).

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** You suspect that the attacker might be moving laterally within the network. Investigate if there is any evidence of file transfers or remote execution between the target host (192.168.50.5) and the next-target host (192.168.50.6).
**Hint:** Check the system logs and configuration files for any evidence of lateral movement.
**Validation:** The task is considered successful if the student identifies the service (payload-transfer.service) responsible for the lateral movement.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. It focuses on the investigation and response to the Kobalos malware compromise, with tasks that are feasible within the given topology and Ansible configuration. The tasks are designed to challenge the student's incident response skills while adhering to the constraints and requirements provided.