### Scenario: GafGyt Backdoor Investigation

**INFO_LEVEL:**
The target network has been experiencing unusual activity. Your task is to investigate and respond to a potential GafGyt backdoor infection. The malware is known to target DVR devices and execute commands to download and run binaries for different architectures (ARM, MIPS, MIPSel). It replaces the standard 'busybox' binary with one of the downloaded binaries.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name should be identified and investigated.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Examine the systemd timers and services to find any suspicious configurations.
**Validation:** The persistence mechanism should be identified and described.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Investigate the files and directories related to the suspicious service.
**Validation:** The filename or file path should be identified and investigated.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.