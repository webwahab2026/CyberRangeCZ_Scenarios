# Linux.Proxy.10 Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious scheduled tasks. Your task is to investigate and respond to this potential compromise.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious scheduled tasks on the victim host.
**Objective:** Identify and analyze any unauthorized or suspicious scheduled tasks that may be related to the malware.
**Hint:** Check the systemd timers and services that are running on the system.

## TRAINING_LEVEL 2
**Task:** Locate files installed by the malware on the compromised host.
**Objective:** Find any files that were introduced by the trojan and analyze their contents.
**Hint:** Look for hidden directories and unusual file paths that may contain malware components.

## TRAINING_LEVEL 3
**Task:** Determine the external host communicating with the compromised system.
**Objective:** Analyze network connections to identify the command-and-control server.
**Hint:** Check the network connections and logs to find any suspicious outbound connections.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Linux.Proxy.10 trojan, focusing on identifying suspicious services, scheduled tasks, files, and network connections. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and artifacts present in the provided data.