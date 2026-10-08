# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

### Hint
Focus on unusual services, persistent processes, and network connections that don't match normal operational patterns.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate and identify the suspicious service running on the target host.

**Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Hint:** Check systemd services and look for any that don't match standard system services.

**Validation:** The service name is systemkernelservicedefender.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:** Examine systemd timers and services related to the suspicious service.

**Validation:** The persistence mechanism is the systemd timer lab-checkin.timer.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Objective:** Correlate events across hosts to identify attacker lateral movement.

**Hint:** Check for any scripts or services that transfer files between hosts.

**Validation:** The service name is payload-transfer.service.