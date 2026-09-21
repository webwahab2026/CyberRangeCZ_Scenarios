# Mirai Trojan Investigation Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and elevated CPU usage. Your task is to investigate and determine the cause of this activity.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the systemd timers on the victim host to identify any suspicious or unauthorized scheduled tasks.

**Hint:** Use the `systemctl list-timers` command to list all active timers and examine their associated services.

**Validation:** The hidden flag is the name of the suspicious timer.

## TRAINING_LEVEL 2
**Task:** Examine the system logs to identify any unusual or unauthorized services that have been started or stopped recently.

**Hint:** Use the `journalctl` command to review system logs, focusing on service-related events.

**Validation:** The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 3
**Task:** Investigate the network connections on the victim host to identify any unauthorized or suspicious outbound connections.

**Hint:** Use the `ss` or `netstat` command to list all active network connections and examine their destinations.

**Validation:** The hidden flag is the IP address of the command-and-control server.