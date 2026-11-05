# KrustyLoader Investigation

## INFO_LEVEL
The victim host has exhibited suspicious behavior, including unauthorized network connections and unusual file modifications. Your task is to investigate the compromise, identify the malware, and determine the extent of the intrusion.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on the compromised host.

**Step-by-step solution:**
1. Log in to the victim host using the provided credentials.
2. List all running services using the command: `systemctl list-units --type=service --state=running`
3. Identify the suspicious service named `session-mgr.timer`.
4. Inspect the service details using the command: `systemctl cat session-mgr.timer`
5. Note the service name `session-mgr.service` and inspect its details using the command: `systemctl cat session-mgr.service`
6. The hidden flag is the name of the suspicious service.

**Hints:**
1. Use the command `systemctl list-units --type=service --state=running` to list all running services.
2. Look for services with unusual or generic names that might indicate malicious activity.
3. Use the command `systemctl cat <service_name>` to inspect the details of a suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity.

**Step-by-step solution:**
1. List all active timers using the command: `systemctl list-timers --all`
2. Identify the suspicious timer named `session-mgr.timer`.
3. Inspect the timer details using the command: `systemctl cat session-mgr.timer`
4. Note the schedule defined in the timer, which indicates periodic execution.
5. The hidden flag is the name of the suspicious timer.

**Hints:**
1. Use the command `systemctl list-timers --all` to list all active timers.
2. Look for timers with unusual or generic names that might indicate malicious activity.
3. Use the command `systemctl cat <timer_name>` to inspect the details of a suspicious timer.

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Step-by-step solution:**
1. Navigate to the suspicious directory using the command: `cd /tmp/.session`
2. List the contents of the directory using the command: `ls -la`
3. Identify the suspicious files named `rat.sh` and `stealer.sh`.
4. The hidden flag is the name of one of the suspicious files.

**Hints:**
1. Look for directories with unusual or hidden names that might contain malicious files.
2. Use the command `ls -la` to list the contents of a directory, including hidden files.
3. Investigate files with unusual or generic names that might indicate malicious activity.