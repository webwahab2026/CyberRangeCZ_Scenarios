Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: BlackTech PLEAD Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the BlackTech threat group. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host (192.168.50.5) with the following credentials:
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host (192.168.50.5) to an unknown destination. Investigate this activity and identify the service responsible for these connections.

**Hint:**
Check running services and their network connections.

**Validation:**
The service name is stored in /tmp/flag1.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the system's startup configuration to find how this service is automatically started.

**Hint:**
Check systemd service configurations and timers.

**Validation:**
The persistence identifier is stored in /tmp/flag2.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement. Determine if the suspicious service is transferring data to other hosts in the network.

**Hint:**
Check for scheduled tasks and file transfer activities.

**Validation:**
The service name is stored in /tmp/flag3.

---

This scenario aligns with the provided sandbox environment and MISP event, focusing on investigating the PLEAD backdoor malware's behavior. The tasks are designed to test the student's ability to identify suspicious services, analyze persistence mechanisms, and investigate lateral movement, all of which are relevant to the Incident Response security profile.

The scenario uses only the hosts, services, and file paths that exist in the sandbox environment as described by the topology and Ansible configuration. The validation flags are stored in temporary files that can be created during the scenario setup.