### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate and respond to this incident. The Fysbis backdoor is a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of ELF binaries and can install itself with or without root privileges.

**ACCESS_LEVEL:**
- Entry Host: `target` (IP: 192.168.50.5)
- Username: `cyrano`
- Password: `cyrano`

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `systemkernelservicedefender.service` should be identified.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Investigate the systemd service configuration and timers.
**Validation:** The persistence mechanism should be identified as a systemd timer `lab-checkin.timer`.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Check the scripts and executables associated with the suspicious service.
**Validation:** The filename `/usr/local/bin/lab-checkin.sh` should be identified.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and artifacts within the sandbox environment, ensuring a realistic and deployable exercise.