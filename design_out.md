# Whirlpool Malware Investigation

## INFO_LEVEL
The Barracuda Email Security Gateway (ESG) device in your network has exhibited unusual behavior. Initial analysis suggests the presence of the WHIRLPOOL malware variant Linux/WhirlPool.A, a Linux ELF reverse shell. Your task is to investigate and respond to this potential security incident.

## ACCESS_LEVEL
You have SSH access to the target system with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target system for suspicious services or processes.

**Question:** What service or process appears suspicious on the target system?

**Hint:** Check running services and processes, looking for anything unusual or unexpected.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What persistence mechanism is being used by the suspicious service?

**Hint:** Investigate systemd services and timers that might be responsible for starting the suspicious service.

## TRAINING_LEVEL 3
**Task:** Identify the file associated with the suspicious activity and analyze its contents.

**Question:** What is the name and path of the file associated with the suspicious activity, and what does it contain?

**Hint:** Look for unusual files in the home directory of the user and analyze their contents.

## Validation
The scenario is aligned with the provided MISP event, security profile, topology, and Ansible configuration. All tasks are feasible within the sandbox environment and rely on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The scenario uses only indicators explicitly present in the MISP event for threat intelligence elements.