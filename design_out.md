# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Description:**
While monitoring the target host, you noticed unusual network activity. Investigate the target host to identify any suspicious services or processes that might be responsible for this activity.

**Hint:**
Check running services and processes, looking for anything unusual or unexpected.

**Validation:**
The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence.

**Description:**
You've identified a suspicious service running on the target host. Determine how this service is automatically started after a system reboot.

**Hint:**
Investigate systemd services, cron jobs, or other persistence mechanisms.

**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

## TRAINING_LEVEL 3
**Task:** Investigate lateral movement to other hosts.

**Description:**
You suspect that the attacker might be moving laterally from the target host to other systems in the network. Investigate any evidence of file transfers or remote execution that could indicate lateral movement.

**Hint:**
Check for any scripts or services that transfer files or execute commands on other hosts.

**Validation:**
The hidden flag is the name of the service or script used for lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks focus on investigating the Sofacy Fysbis backdoor, identifying its persistence mechanisms, and detecting lateral movement within the network. The scenario adheres to the strict constraints of using only indicators present in the MISP event and the realistic artifacts derived from the sandbox topology and Ansible configuration.