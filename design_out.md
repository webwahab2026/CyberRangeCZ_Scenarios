# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can access other hosts in the network.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers that might be responsible for starting the suspicious service.

## TRAINING_LEVEL 3
**Task:** Identify the file or executable associated with the suspicious service.

**Question:** What is the path to the executable or file associated with the suspicious service?

**Hint:** Look for unusual files in the user's home directory or system directories that might be related to the suspicious service.

## Answer Key
1. bkd.service
2. systemd timer
3. /usr/local/bin/lab-checkin.sh