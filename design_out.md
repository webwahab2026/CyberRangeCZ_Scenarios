# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can access other hosts in the network.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Description:**
While monitoring the target host, you noticed unusual network activity. Investigate the host to identify any suspicious services or processes that might be responsible for this activity.

**Hint:**
Check running services and processes, looking for anything unusual or unauthorized.

**Validation:**
The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence.

**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. This will help you understand how the attacker ensures the service continues to run even after reboots.

**Hint:**
Investigate system startup configurations and scheduled tasks.

**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

## TRAINING_LEVEL 3
**Task:** Investigate lateral movement between hosts.

**Description:**
Examine the target host for evidence of lateral movement to other hosts in the network. Identify any file transfers or remote execution that might indicate the attacker is moving laterally.

**Hint:**
Check for any scheduled file transfers or remote execution tasks.

**Validation:**
The hidden flag is the name of the service, filename, or destination host used for lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is feasible within the given topology and Ansible configuration, and all indicators are derived from the MISP event or the sandbox details. The tasks focus on investigating and responding to the Sofacy Fysbis backdoor, with a defense-oriented approach suitable for an intermediate difficulty level.