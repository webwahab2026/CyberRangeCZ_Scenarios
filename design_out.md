# XMRig Cryptominer Investigation

## INFO_LEVEL
The IT department has received reports of unusually high CPU usage on several Linux servers in the network. Initial investigations suggest that one of the servers might be running unauthorized cryptocurrency mining software. Your task is to investigate these systems, identify the source of the problem, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the `miner-host` system with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` system to identify any unauthorized or suspicious services running on the system.

**Solution:**
1. SSH into the `miner-host` system using the provided credentials.
2. List all running services using the command: `systemctl list-units --type=service`
3. Look for any suspicious or unauthorized services. Pay attention to services with unusual names or those that you don't recognize.
4. Investigate the suspicious service by checking its status, configuration, and executable path.

**Hint 1:** Use the command `systemctl status <service_name>` to check the status and details of a specific service.
**Hint 2:** Check the executable path of the service to see if it points to a suspicious location.
**Hint 3:** Look for services that might be related to system monitoring or hardware performance, as these could be disguising malicious activity.

**Hidden Flag:** sys-monitor.service

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for the abnormal CPU or resource utilization on the `miner-host` system.

**Solution:**
1. SSH into the `miner-host` system using the provided credentials.
2. Check the running processes and their resource usage with the command: `top`
3. Look for any processes consuming a high percentage of CPU resources.
4. Investigate the suspicious process by checking its name, path, and user.
5. Use the command `ps aux | grep <process_name>` to gather more information about the process.

**Hint 1:** Pay attention to processes with high CPU usage percentages.
**Hint 2:** Check the process name and path to see if they look suspicious or unusual.
**Hint 3:** Look for processes that might be related to system monitoring or hardware performance, as these could be disguising malicious activity.

**Hidden Flag:** sys-monitor

## TRAINING_LEVEL 3
**Task:** Determine the external host communicating with the compromised `miner-host` system for cryptocurrency mining.

**Solution:**
1. SSH into the `miner-host` system using the provided credentials.
2. Check the network connections using the command: `netstat -tulnp`
3. Look for any suspicious outbound connections, especially those to external hosts.
4. Investigate the suspicious connection by checking the destination IP address and port.
5. Use the command `curl -v <destination_IP>:<port>` to gather more information about the connection.

**Hint 1:** Pay attention to outbound connections to external hosts, especially those on unusual ports.
**Hint 2:** Check the destination IP address and port to see if they match known mining pool or command-and-control servers.
**Hint 3:** Look for connections that might be related to system monitoring or hardware performance, as these could be disguising malicious activity.

**Hidden Flag:** 192.168.40.5