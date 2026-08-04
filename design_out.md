### Scenario: BlackTech PLEAD Backdoor Investigation

**INFO_LEVEL:**
The organization has detected unusual network activity originating from the target host. Initial analysis suggests a potential compromise by the BlackTech group using the PLEAD backdoor malware. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:** Users have reported slow network performance. Investigate the target host for any suspicious network activity that could be causing this issue.
**Hint:** Check the network connections and running services on the target host.
**Validation:** The student should identify the suspicious service running on port 4444.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:** A suspicious service has been identified. Analyze this service to determine its purpose and potential impact on the system.
**Hint:** Examine the service configuration and logs to understand its behavior.
**Validation:** The student should identify that the service is a backdoor listener and note its persistence mechanism.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** Evidence suggests that the attacker may have moved laterally to another host. Investigate the target host for any signs of lateral movement.
**Hint:** Check for any file transfers or remote execution commands.
**Validation:** The student should identify the rsync command used for lateral movement and the destination host (next-target).

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are designed to be feasible within the sandbox environment and focus on investigating the PLEAD backdoor malware and its associated activities.