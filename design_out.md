Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: XOR.DDoS Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity on its Linux servers. As an incident responder, your task is to investigate and contain the threat. The compromised systems may be part of a larger botnet involved in distributed denial-of-service (DDoS) attacks.

**ACCESS_LEVEL:**
You have SSH access to the target server with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:** Users have reported slow network performance. Investigate the target server for any suspicious network activity that could be causing this issue.
**Hint:** Check running services and network connections.
**Validation:** The student should identify the suspicious service listening on port 4444.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:** You've identified a suspicious service. Analyze it to determine its purpose and potential impact on the system.
**Hint:** Examine the service configuration and related files.
**Validation:** The student should find the service named "bkd.service" and identify its connection to the c2-server.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** Check if the attacker has moved laterally to other systems within the network.
**Hint:** Look for any unusual file transfers or remote connections.
**Validation:** The student should discover the payload-transfer service and its connection to the next-target host.

---

This scenario aligns with the provided MISP event about the XOR.DDoS malware family and the Groundhog backdoor. It also matches the Incident Response security profile and the sandbox environment described in the topology and Ansible configuration. The tasks are designed to guide students through investigating and containing the threat while adhering to the constraints and guidelines provided.