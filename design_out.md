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
**Task:** Investigate the suspicious scheduled tasks on the victim host.
**Objective:** Identify and investigate any unauthorized or suspicious scheduled tasks that may be responsible for automatically executing malware.
**Hint:** Check the systemd timers and services that are enabled and running.

## TRAINING_LEVEL 2
**Task:** Locate files installed by the malware on the compromised host.
**Objective:** Correlate suspicious activity with files introduced by the trojan.
**Hint:** Look for unusual directories and files, especially those in non-standard locations.

## TRAINING_LEVEL 3
**Task:** Determine the external host communicating with the compromised system.
**Objective:** Analyze network connections and identify the command-and-control server.
**Hint:** Check the network connections and logs for any suspicious outbound connections.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.