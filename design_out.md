# Tsunami/Kaiten Incident Response Scenario

## INFO_LEVEL
The target system has exhibited unusual network activity, including unexpected outbound connections to an unknown server. Initial analysis suggests the presence of a backdoor trojan with IRC bot capabilities. Your task is to investigate and respond to this potential security incident.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Objective:** Identify and investigate an unauthorized or suspicious service running on the target system.

**Hint:** Check the system logs and running processes for any unusual activity.

**Validation:** The student should identify the suspicious service running on port 4444.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:** Examine the systemd services and timers.

**Validation:** The student should identify the systemd service and timer responsible for the suspicious activity.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Objective:** Correlate events across hosts to identify attacker lateral movement.

**Hint:** Check the logs for any file transfers or remote execution commands.

**Validation:** The student should identify the service name, filename, or destination host used for lateral movement.