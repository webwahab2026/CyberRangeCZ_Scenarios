Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Earth Lusca Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Earth Lusca malware family. Your team has been tasked with investigating and responding to this potential security incident. The malware, known as KTLVdoor, is a backdoor that enables multiplatform intrusion, command and control (C2) communication, lateral movement, data exfiltration, and persistence.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious Network Activity Investigation
**Description:**
While monitoring network traffic, you've noticed unusual outbound connections from the target host (192.168.50.5) to an unknown destination. Investigate this activity and identify the service responsible for these connections.
**Hint:** Check the systemd services and their associated network activity.
**Validation:** The service name (bkd.service) must be identified.

**TRAINING_LEVEL 2:**
**Task:** Persistence Mechanism Analysis
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the persistence mechanism and gather information about how it's configured to start automatically.
**Hint:** Examine the service unit file and its dependencies.
**Validation:** The persistence mechanism (systemd service) and its unit file path (/etc/systemd/system/bkd.service) must be identified.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:**
You've discovered that the suspicious service is transferring files to another host in the network. Investigate this lateral movement activity and identify the destination host, the transferred files, and the mechanism used for the transfer.
**Hint:** Check the systemd timers and their associated scripts.
**Validation:** The destination host (next-target), the transferred files (payload-transfer.log), and the transfer mechanism (rsync over SSH) must be identified.

---

This scenario is strictly aligned with the provided sandbox environment, MISP event, and security profile. The tasks are designed to guide students through the investigation and response process while adhering to the constraints and requirements outlined in the system prompt. The scenario focuses on the Earth Lusca malware family and its associated behavior, as described in the MISP event, and leverages the services, hosts, and configurations defined in the topology and Ansible data.