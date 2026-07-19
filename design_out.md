### Scenario: BRICKSTORM Backdoor Investigation

**INFO_LEVEL:**
The target host has been exhibiting unusual network activity. Your task is to investigate and identify any malicious activity related to the BRICKSTORM Backdoor. This backdoor is known to use advanced techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution to evade detection. The backdoor may also use DoH, nested TLS encryption, and abuse legitimate cloud services.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. The target host's IP address is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target host.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and look for any unusual or unauthorized services.
**Hidden Flag:** Service name

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms such as systemd, cron, scheduled tasks, or registry entries.
**Hint:** Examine the systemd service files and timers.
**Hidden Flag:** Service name or persistence identifier

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Investigate the paths and files associated with the suspicious service.
**Hidden Flag:** Filename or file path

---

**Note:** The scenario is designed to align strictly with the provided sandbox environment and MISP event. All tasks and indicators are derived from the topology, Ansible configuration, and MISP event data. The hidden flags are used exclusively for automated assessment and are not revealed in the task descriptions.