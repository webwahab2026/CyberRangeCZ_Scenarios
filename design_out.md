# Sandworm Exaramel Incident Response Scenario

## INFO_LEVEL
The target system has exhibited unusual network activity, including unexpected outbound connections. Initial analysis suggests potential compromise by the Sandworm group using the Exaramel backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target system.

**Question:** What is the destination IP address and port of the suspicious outbound connections?

**Hint:** Check the system logs and network connections to identify any unusual outbound traffic.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious activity is maintained on the target system.

**Question:** What is the name of the service responsible for the suspicious activity?

**Hint:** Investigate the systemd services and cron jobs to find any unusual entries.

## TRAINING_LEVEL 3
**Task:** Identify the malicious artifact associated with the suspicious activity.

**Question:** What is the path to the malicious executable or file?

**Hint:** Look for unusual files in the home directory of the user `cyrano` and check the file permissions and ownership.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.