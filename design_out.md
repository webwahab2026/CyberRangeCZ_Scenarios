# Sandworm Incident Response Exercise

## INFO_LEVEL
The Centreon IT infrastructure has been compromised by the Sandworm intrusion set. Your team has detected unusual network activity and needs to investigate and respond to this security incident. The P.A.S. webshell malware has been identified as the threat actor's tool of choice.

## ACCESS_LEVEL
You have SSH access to the target server with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Activity
**Description:** Your network monitoring tools have detected unusual outbound connections from the target server. Investigate this activity to identify any suspicious services or processes that might be responsible.
**Hint:** Check running services and network connections to identify any anomalies.
**Validation:** The student should identify the suspicious service running on port 4444.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanism
**Description:** Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the system's startup mechanisms to find any unauthorized configurations.
**Hint:** Look for systemd services or cron jobs that might be responsible for starting the suspicious service.
**Validation:** The student should identify the systemd service unit file responsible for the suspicious service.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** The attacker might be using this server as a foothold to move laterally within the network. Investigate any evidence of file transfers or remote execution that could indicate lateral movement to other hosts.
**Hint:** Check for any scheduled tasks or scripts that might be transferring files to other hosts.
**Validation:** The student should identify the script and systemd timer responsible for transferring files to the next-target host.