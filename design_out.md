# Scenario: Linux.Mirai Incident Response

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and suspicious scheduled tasks. Your task is to investigate and respond to this potential compromise involving the Linux.Mirai trojan.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and identify any that appear unauthorized or suspicious.
**Hint:** Check the status of all services and look for any that are not part of the standard system configuration.

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing unauthorized processes.
**Objective:** Identify scheduled execution persistence mechanisms that might be used to maintain unauthorized access.
**Hint:** Examine the systemd timers and services to find any that are not part of the standard system configuration.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the unauthorized processes on the compromised host.
**Objective:** Correlate suspicious activity with files introduced by the unauthorized processes.
**Hint:** Search for files in unusual or hidden directories that might be related to the suspicious services or scheduled tasks.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise for incident response training.