### Scenario: BlackTech PLEAD Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the BlackTech threat group using the PLEAD backdoor malware. Your task is to investigate and respond to this incident. The malware is known to establish command and control (C2) communication, perform lateral movement, and exfiltrate data. The compromised hosts are running Ubuntu.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised hosts and take necessary actions.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name should be identified and investigated.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot on the `target` host.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Examine the systemd service files and timers.
**Validation:** The persistence mechanism should be identified and described.

**TRAINING_LEVEL 3:**
**Task:** Identify file transfers or remote execution used to move between hosts from the `target` host to the `next-target` host.
**Objective:** Correlate events across hosts to identify attacker lateral movement.
**Hint:** Check the logs and systemd services related to file transfers.
**Validation:** The service name, filename, or destination host should be identified and described.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.