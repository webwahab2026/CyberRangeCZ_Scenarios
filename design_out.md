### Scenario: ELF_IMEIJ.A Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the ELF_IMEIJ.A backdoor malware. This malware exploits a vulnerability in AVTech devices to execute a command injection that triggers the malware download. It gathers system information and network activity data, executes shell commands from the malicious actor, initiates DDoS attacks, and can terminate itself. Your task is to investigate and mitigate this threat.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and take necessary actions.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `Arm1.service` should be identified as suspicious.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Investigate the systemd service configuration files and timers.
**Validation:** The persistence mechanism should be identified as the systemd service `Arm1.service` and its associated timer.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Check the logs and configuration files related to the suspicious service.
**Validation:** The file `/home/cyrano/Arm1` should be identified as the malicious artifact.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.