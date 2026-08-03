# Sandworm Exaramel Backdoor Investigation

## INFO_LEVEL
The target system has exhibited unusual network activity, including unexpected outbound connections to an unknown server. Initial analysis suggests the presence of a backdoor trojan known as Exaramel, associated with the Sandworm threat group. Your task is to investigate and respond to this potential compromise.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`. You also have access to the next-target system with the same credentials.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Question:** What is the destination IP address and port of the suspicious outbound connections?

**Hint:** Check the system logs and network connections for any unusual patterns.

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for the suspicious network activity.

**Question:** What is the name of the process making the suspicious outbound connections?

**Hint:** Use process monitoring tools to correlate network activity with running processes.

## TRAINING_LEVEL 3
**Task:** Determine how the malicious process maintains persistence on the system.

**Question:** What is the persistence mechanism used by the malicious process?

**Hint:** Check systemd services, cron jobs, and other scheduled tasks for any unusual entries.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Exaramel backdoor, identifying its network activity, process, and persistence mechanism, which are all critical aspects of incident response. The scenario adheres to the sandbox constraints and uses only the indicators and artifacts present in the provided data.