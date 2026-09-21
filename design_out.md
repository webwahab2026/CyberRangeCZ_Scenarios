# Scenario: Linux.Mirai Incident Response

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and suspicious scheduled tasks. Your task is to investigate and respond to this potential compromise.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on the victim host.
**Description:** While monitoring the victim host, you noticed an unusual service running. Investigate this service to determine if it is legitimate or malicious.
**Hint:** Check the list of running services and look for any that appear out of place or have unusual descriptions.
**Flag:** The name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Identify the scheduled task responsible for executing the malware.
**Description:** The suspicious service appears to be triggered by a scheduled task. Identify the task that is responsible for automatically executing the malware.
**Hint:** Check the systemd timers and look for any that are associated with the suspicious service.
**Flag:** The name of the scheduled task or timer.

## TRAINING_LEVEL 3
**Task:** Locate the files installed by the malware on the compromised host.
**Description:** The malware has likely installed files on the victim host. Locate these files to understand the extent of the compromise.
**Hint:** Search for files in unusual or hidden directories that may have been created or modified by the malware.
**Flag:** The name of a file installed by the malware.