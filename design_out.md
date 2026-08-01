# Linux.Proxy Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Linux.Proxy.10 trojan, which is designed to run a SOCKS5 proxy server on the infected device. This trojan is used by cybercriminals to maintain anonymity online. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for any unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and distinguish legitimate services from trojan-related services.
**Hint:** Check the status of all services and look for any that appear unusual or out of place.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing the malware on the victim host.
**Objective:** Identify scheduled execution persistence mechanisms (e.g., cron, systemd timers, Windows Scheduled Tasks).
**Hint:** Examine the systemd timers and services to find any that might be related to the malware.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the compromised host.
**Objective:** Correlate suspicious activity with files introduced by the trojan.
**Hint:** Search for hidden directories and files that might contain malware components or collected data.