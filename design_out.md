### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity, including intermittent connections to an unknown external server. Initial analysis suggests the presence of a backdoor trojan known as Fysbis, associated with the Sofacy malware family. Your task is to investigate and respond to this potential compromise.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target system.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `dbus-notifier.service` should be identified as suspicious.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Examine the systemd service files and timers.
**Validation:** The persistence mechanism should be identified as the systemd service `dbus-notifier.service` and its associated timer.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Investigate the files in the home directory of the user `cyrano`.
**Validation:** The file `/home/cyrano/dbus-inotifier` should be identified as associated with the suspicious activity.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.