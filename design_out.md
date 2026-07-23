# BRICKSTORM Backdoor Investigation

## INFO_LEVEL
The target system has exhibited unusual network activity, including unexpected outbound connections to an unknown server. Your task is to investigate and determine the nature of this activity.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the `192.168.50.0/24` network.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Question:** What is the destination IP address and port of the suspicious outbound connections?

**Hint:** Check the system logs and network connections to identify any unusual patterns.

## TRAINING_LEVEL 2
**Task:** Determine the process responsible for the suspicious network activity.

**Question:** What is the name of the process making the suspicious outbound connections?

**Hint:** Use process enumeration tools to identify running processes and their network activity.

## TRAINING_LEVEL 3
**Task:** Investigate the persistence mechanism used by the suspicious process.

**Question:** How is the suspicious process automatically started after a system reboot?

**Hint:** Check systemd services, cron jobs, and other persistence mechanisms to find how the process is maintained.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and mitigating the BRICKSTORM Backdoor threat.