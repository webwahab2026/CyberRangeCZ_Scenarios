# ELF_IMEIJ Incident Response Scenario

## INFO_LEVEL
The AVTech devices in your network have been compromised by the ELF_IMEIJ.A backdoor malware. This malware is known to exploit vulnerabilities in AVTech devices to execute command injection and download malicious files. It gathers system information, executes shell commands, initiates DDoS attacks, and can terminate itself. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unfamiliar services.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Examine the systemd service files and timers to find any suspicious configurations.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.
**Objective:** Correlate events across hosts to identify attacker lateral movement.
**Hint:** Check the logs and systemd timers for any evidence of file transfers or remote execution.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.