# Linux/NyaDrop Incident Response Scenario

## INFO_LEVEL
The target system has exhibited unusual network activity. Your task is to investigate and respond to this potential security incident involving the Linux/NyaDrop malware.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the 192.168.50.0/24 network.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Objective:** Identify and investigate an unauthorized or suspicious service running on the target system.

**Hint:** Check the running services and network connections on the target system.

**Validation:** The student should identify the suspicious service running on port 4444.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:** Check the systemd services and timers on the target system.

**Validation:** The student should identify the systemd service and timer responsible for the suspicious activity.

## TRAINING_LEVEL 3
**Task:** Investigate the file transfers or remote execution used to move between hosts.

**Objective:** Correlate events across hosts to identify attacker lateral movement.

**Hint:** Check the logs and network connections on both the target and next-target systems.

**Validation:** The student should identify the service name, filename, or destination host used for lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.