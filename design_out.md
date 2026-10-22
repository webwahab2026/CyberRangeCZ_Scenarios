Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Linux.Bew Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on its Linux servers. As an incident responder, your task is to investigate and contain the threat. The malware in question is known as Linux.Bew, a backdoor designed for Bitcoin mining that establishes communication with a command and control server and performs lateral movement within the network.

**ACCESS_LEVEL:**
You have SSH access to the target server with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring the target server, you've noticed unusual outbound network connections. Investigate these connections to identify any suspicious activity.
**Hint:** Check the network connections and listen ports on the target server.
**Validation:** The task is considered successful if the student identifies the suspicious port (443) used for C2 communication.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:** The suspicious service appears to be persistent across reboots. Investigate how this service maintains persistence on the target server.
**Hint:** Examine the systemd services and timers on the target server.
**Validation:** The task is considered successful if the student identifies the persistence mechanism (systemd timer and service for payload transfer).

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** Evidence suggests that the attacker may be attempting to move laterally within the network. Investigate any file transfers or remote execution used to move between hosts.
**Hint:** Check the systemd services and scripts related to file transfers on the target server.
**Validation:** The task is considered successful if the student identifies the lateral movement mechanism (systemd service and script for payload transfer to next-target).

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating the Linux.Bew backdoor, identifying its persistence mechanism, and analyzing its lateral movement capabilities. The scenario adheres to the security profile of an Incident Responder and follows the guidelines for exercise generation.