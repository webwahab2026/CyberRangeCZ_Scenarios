Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Sofacy Fysbis Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Sofacy group's Fysbis malware. Your task is to investigate and respond to this potential compromise.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host to port 80. Investigate this activity and identify the service responsible for these connections.
**Hint:** Check running services and their network connections.
**Validation:** The service name should be identified.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the system's startup mechanisms to find how this service is automatically started.
**Hint:** Check systemd services and timers.
**Validation:** The persistence mechanism (service name or timer) should be identified.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement. Determine if the suspicious service is transferring files to other hosts in the network.
**Hint:** Check for file transfer services and their logs.
**Validation:** The service name, filename, or destination host should be identified.

---

This scenario aligns with the provided sandbox environment and MISP event, focusing on the Sofacy group's Fysbis malware. The tasks are designed to investigate suspicious network activity, analyze persistence mechanisms, and examine potential lateral movement, all within the constraints of the available sandbox infrastructure. The scenario follows the NICE Incident Response profile and uses only indicators and artifacts present in the MISP event and sandbox configuration.