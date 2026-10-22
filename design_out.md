### Scenario: Xbash Incident Response

#### INFO_LEVEL
The organization has detected unusual network activity on its Linux-based systems. Initial analysis suggests a potential Xbash malware infection, which combines ransomware, coinmining, and botnet capabilities. Your task is to investigate and respond to this incident.

#### ACCESS_LEVEL
- **Entry Host:** target (IP: 192.168.50.5)
- **Username:** cyrano
- **Password:** cyrano

#### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:** Investigate the target host for any unauthorized or suspicious services running. Identify any services that appear out of place or exhibit unusual behavior.
**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check the systemd services and running processes.

#### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:** Determine how the suspicious service identified in the previous task is automatically started after reboot. Investigate the persistence mechanisms used.
**Learning Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Look for systemd service files and timers.

#### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:** Identify any file transfers or remote execution used to move between hosts. Investigate the lateral movement techniques employed by the attacker.
**Learning Objective:** Correlate events across hosts to identify attacker lateral movement.
**Hint:** Check the rsync logs and SSH connections.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and focuses on realistic investigation and response activities.