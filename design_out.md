### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromise, identify the indicators of compromise (IOCs), and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromise and move laterally to other hosts if necessary.

#### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `systemkernelservicedefender.service` should be identified as suspicious.

#### TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Investigate the systemd service configuration and look for any unusual or unauthorized configurations.
**Validation:** The persistence mechanism should be identified as a systemd service unit file located at `/etc/systemd/system/systemkernelservicedefender.service`.

#### TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Check the service configuration and look for any unusual or unauthorized executable paths.
**Validation:** The executable or file associated with the suspicious activity should be identified as `/usr/local/bin/lab-checkin.sh`.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through the investigation process while adhering to the constraints and requirements specified.