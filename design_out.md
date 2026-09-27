Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: BlackTech PLEAD Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the BlackTech threat group. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host. Investigate this activity and identify any suspicious services or processes that might be responsible.

**Hint:**
Check running services and network connections on the target host.

**Validation:**
The system will validate that you've identified the correct suspicious service.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the startup mechanisms and configuration files.

**Hint:**
Look for systemd services or cron jobs that might be responsible for starting the suspicious service.

**Validation:**
The system will validate that you've identified the correct persistence mechanism.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement. Determine if the attacker has attempted to move to other systems within the network.

**Hint:**
Check for any unusual file transfers or remote execution attempts.

**Validation:**
The system will validate that you've identified the correct evidence of lateral movement.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating the PLEAD backdoor malware, which is known for its command and control (C2) communication, lateral movement, and exfiltration capabilities. The scenario follows the NICE Incident Response profile and uses only the indicators and hosts present in the provided data.

The scenario includes three training level tasks that guide the student through the investigation process, from identifying suspicious network activity to analyzing persistence mechanisms and investigating lateral movement. Each task is designed to be technically feasible within the sandbox environment and aligns with the capabilities of the PLEAD malware as described in the MISP event.