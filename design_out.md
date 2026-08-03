### Scenario: ELF_IMEIJ Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the ELF_IMEIJ.A backdoor malware. This malware exploits a vulnerability in AVTech devices to execute command injection, which triggers the malware download. The malware gathers system information and network activity data, executes shell commands from the malicious actor, initiates DDoS attacks, and can terminate itself. Your task is to investigate and mitigate this threat.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and take necessary actions.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Validation:** The service name `CloudSetup.cgi.service` should be identified as suspicious.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Investigate the systemd units and timers related to the suspicious service.
**Validation:** The persistence mechanism should be identified as the systemd unit `CloudSetup.cgi.service` and timer `lab-checkin.timer`.

**TRAINING_LEVEL 3:**
**Task:** Identify the process responsible for suspicious activity on the `target` host.
**Objective:** Analyze running processes and correlate them with services and network connections.
**Hint:** Use process enumeration tools to identify the process associated with the suspicious service.
**Validation:** The process name `ncat` should be identified as responsible for the suspicious activity.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.