# BRICKSTORM Backdoor Investigation

## INFO_LEVEL
The target system has exhibited unusual network behavior, including unexpected outbound connections to unknown destinations. Your task is to investigate and identify the source of this suspicious activity.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the `192.168.50.0/24` network.

## TRAINING_LEVEL 1
**Task:** Investigate the target system for any unauthorized or suspicious services running on the host.

**Question:** What is the name of the suspicious service running on the target system?

**Hint:** Check the list of running services and look for any that appear unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd services and timers to identify how the service is set to start automatically.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Question:** What is the name of the service responsible for lateral movement between the target and next-target systems?

**Hint:** Investigate the systemd services and timers related to file transfers and remote execution.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the BRICKSTORM backdoor's behavior, including its persistence mechanisms and lateral movement capabilities. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.