### Scenario: Linux.Bew Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity, including unexpected outbound connections to an unknown server. Initial analysis suggests the presence of a backdoor malware known as Linux.Bew, which is used for Bitcoin mining and data exfiltration. Your task is to investigate and respond to this potential security incident.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target system.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `bkd.service` should be identified as suspicious.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Examine the systemd service configuration files for any suspicious entries.
**Validation:** The persistence mechanism should be identified as the systemd service `bkd.service`.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Investigate the service configuration to find the path of the executable.
**Validation:** The filename `/usr/local/bin/lab-checkin.sh` should be identified as the suspicious file.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.