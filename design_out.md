# Adwind/jRAT Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and potential unauthorized access. Your task is to investigate and respond to this security incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and distinguish legitimate services from trojan-related services.
**Hint:** Check the status of all services and look for any that appear unusual or out of place.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing the malware.
**Objective:** Identify scheduled execution persistence mechanisms (e.g., cron, systemd timers, Windows Scheduled Tasks).
**Hint:** Examine the systemd timers and services to find any that might be related to the suspicious activity.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the compromised host.
**Objective:** Correlate suspicious activity with files introduced by the trojan.
**Hint:** Search for hidden directories and files that might contain malware components or collected data.

## Validation
Each task will be validated based on the correct identification of the specified indicators. The scenario will provide feedback on the accuracy of the responses and guide the student through the investigation process.