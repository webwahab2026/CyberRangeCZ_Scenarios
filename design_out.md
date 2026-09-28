# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers that might be responsible for starting the suspicious service.

## TRAINING_LEVEL 3
**Task:** Identify the file associated with the suspicious service and analyze its behavior.

**Question:** What is the name of the file associated with the suspicious service?

**Hint:** Look for unusual files in the home directory of the user and analyze their contents and permissions.

## Answer Section
1. **Answer:** bkd.service
   **Validation:** The answer must match exactly the service name "bkd.service".

2. **Answer:** systemd timer
   **Validation:** The answer must indicate that the persistence mechanism is a systemd timer.

3. **Answer:** lab-checkin.sh
   **Validation:** The answer must match exactly the filename "lab-checkin.sh".