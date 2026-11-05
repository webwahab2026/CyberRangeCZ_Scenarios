# Scenario: Linux.Mirai Incident Response

## INFO_LEVEL
The victim host in your network has been compromised by the Linux.Mirai trojan. This malware is known to target Linux systems, particularly IoT devices, and is capable of performing DDoS attacks by infecting devices and using them as part of a botnet. Your task is to investigate the compromised host, identify the malware's activities, and take appropriate measures to contain and remediate the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity of periodically collecting `/etc/passwd`, home directory listings, and sensitive files, then exfiltrating them to a C2 server.

**Step-by-step solution to find the hidden flag:**
1. List all services on the system using `systemctl list-units --type=service --all`.
2. Look for unfamiliar service names or misspellings of legitimate services.
3. Check the service descriptions and startup behavior for any unusual activity.
4. Identify the service responsible for the suspicious activity.

**Hint 1:** Use the command `systemctl list-units --type=service --all` to list all services.
**Hint 2:** Look for services with unusual descriptions or startup behavior.
**Hint 3:** The service name is related to network diagnostics.

## TRAINING_LEVEL 2
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-step solution to find the hidden flag:**
1. Use `systemctl cat <service>` to inspect the service configuration.
2. Pay particular attention to the `ExecStart` field, which specifies the path to the script launched by the service.
3. Inspect the script to find the port number used for communication.

**Hint 1:** Use the command `systemctl cat <service>` to inspect the service configuration.
**Hint 2:** Look for the `ExecStart` field in the service configuration.
**Hint 3:** The port number is specified in the script launched by the service.

## TRAINING_LEVEL 3
**Task:** Investigators suspect that a mechanism keeps the identified service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-step solution to find the hidden flag:**
1. List all timers on the system using `systemctl list-timers --all`.
2. Look for timers associated with the identified service.
3. Inspect the timer configuration using `systemctl cat <timer>`.
4. Identify the timer responsible for the recurring execution of the service.

**Hint 1:** Use the command `systemctl list-timers --all` to list all timers.
**Hint 2:** Look for timers associated with the identified service.
**Hint 3:** The timer name is related to network diagnostics.