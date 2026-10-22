# Sandworm Exaramel Incident Response Scenario

## INFO_LEVEL
The target system has exhibited unusual network activity and potential unauthorized access. Your task is to investigate and respond to this security incident.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Description:**
The target system has shown suspicious outbound network connections. Your task is to identify and investigate any unauthorized or suspicious services running on the system.

**Hint:**
Check the running services and network connections on the target system.

**Validation:**
The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Description:**
Now that you have identified the suspicious service, you need to find out how it maintains persistence on the system. Investigate the persistence mechanisms used by the service.

**Hint:**
Look for systemd services, cron jobs, or other scheduled tasks that might be responsible for starting the suspicious service.

**Validation:**
The hidden flag is the name of the persistence mechanism or the service unit file.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Description:**
Investigate any evidence of lateral movement from the target system to other systems in the network. Look for file transfers, remote execution, or other indicators of lateral movement.

**Hint:**
Check the logs and systemd timers for any evidence of file transfers or remote execution.

**Validation:**
The hidden flag is the name of the service or script responsible for lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through the investigation and response process while adhering to the constraints and requirements specified.