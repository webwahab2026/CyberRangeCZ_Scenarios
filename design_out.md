# KrustyLoader Investigation

## INFO_LEVEL
The victim host has exhibited unusual network activity and suspicious file modifications. Your task is to investigate the compromise, identify the malware, and determine the extent of the intrusion.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on the compromised host.

**Step-by-step solution:**
1. Log in to the victim host using the provided credentials.
2. List all running services using the command: `systemctl list-units --type=service`
3. Identify the suspicious service named "session-mgr.timer".
4. Inspect the service details using the command: `systemctl cat session-mgr.timer`
5. Note the service name "session-mgr.service" for the hidden flag.

**Hint 1:** Use the command `systemctl list-units --type=service` to list all running services.
**Hint 2:** Look for services that are not part of the standard system services.
**Hint 3:** The suspicious service is related to session management.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity.

**Step-by-step solution:**
1. List all timers using the command: `systemctl list-timers`
2. Identify the timer named "session-mgr.timer".
3. Inspect the timer details using the command: `systemctl cat session-mgr.timer`
4. Note the timer name "session-mgr.timer" for the hidden flag.

**Hint 1:** Use the command `systemctl list-timers` to list all scheduled timers.
**Hint 2:** Look for timers that are not part of the standard system timers.
**Hint 3:** The suspicious timer is related to session management.

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Step-by-step solution:**
1. Navigate to the directory `/tmp/.session` using the command: `cd /tmp/.session`
2. List the files in the directory using the command: `ls -la`
3. Identify the suspicious file named "rat.sh".
4. Note the filename "rat.sh" for the hidden flag.

**Hint 1:** Use the command `cd /tmp/.session` to navigate to the suspicious directory.
**Hint 2:** Look for files that are not part of the standard system files.
**Hint 3:** The suspicious file is related to remote access functionality.