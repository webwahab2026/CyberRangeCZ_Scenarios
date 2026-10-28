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
**Task:** Investigate the systemd timers on the victim host to identify any suspicious scheduled tasks.

**Hint:** Use the `systemctl list-timers` command to list all active timers and examine their associated services.

**Validation:** The hidden flag is the name of the suspicious timer responsible for executing the malware.

## TRAINING_LEVEL 2
**Task:** Examine the system logs to identify any unusual or unauthorized network connections.

**Hint:** Check the logs in `/var/log/syslog` for any suspicious outbound connections, especially those involving netcat or similar networking tools.

**Validation:** The hidden flag is the IP address of the command-and-control server.

## TRAINING_LEVEL 3
**Task:** Investigate the file system for any hidden or unusual directories that may contain malware components.

**Hint:** Look for directories with unusual names or those located in non-standard locations, especially those owned by root.

**Validation:** The hidden flag is the name of the hidden directory used by the malware.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Mirai trojan's behavior, including its persistence mechanisms, network connections, and hidden directories, while adhering to the constraints and requirements specified.