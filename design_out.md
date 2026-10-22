# Tsunami/Kaiten Incident Response Scenario

## INFO_LEVEL
The network has experienced unusual activity that may indicate a compromise. Your task is to investigate and respond to this potential security incident involving the Tsunami/Kaiten malware family.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network connections on the target host.

**Objective:** Identify and investigate an unauthorized or suspicious service running on the target host.

**Hint:** Check the network connections and running services on the target host.

**Validation:** The service name is -bash.service

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:** Examine the systemd services and timers on the target host.

**Validation:** The service name is -bash.service

## TRAINING_LEVEL 3
**Task:** Investigate the file transfers between the target and next-target hosts.

**Objective:** Identify file transfers or remote execution used to move between hosts.

**Hint:** Check the systemd services and logs related to file transfers on the target host.

**Validation:** The service name is payload-transfer.service