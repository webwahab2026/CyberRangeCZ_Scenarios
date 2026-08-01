### Scenario: Supreme Backdoor Factory Investigation

**INFO_LEVEL:**
The organization has detected unusual network activity originating from the target host. Your task is to investigate and respond to this potential security incident involving the Supreme Backdoor malware family.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
You have observed unusual outbound network connections from the target host. Identify the service or process responsible for this activity.
**Learning Objective:** Enumerate running services and processes to identify suspicious network activity.
**Hint:** Check running services and their associated network connections.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Determine how the suspicious service maintains persistence on the target host. Identify the method used to ensure the service starts automatically after a reboot.
**Learning Objective:** Identify persistence mechanisms such as systemd services or cron jobs.
**Hint:** Examine systemd services and timers.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement to other hosts in the network. Identify any file transfers or remote execution activities.
**Learning Objective:** Correlate events across hosts to identify lateral movement techniques.
**Hint:** Check for rsync activities and SSH connections to other hosts.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise within the KYPO/CyberRangeCZ environment.