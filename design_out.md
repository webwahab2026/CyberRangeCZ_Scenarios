# Linux.Bew Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Linux.Bew backdoor malware. This malware is designed for Bitcoin mining and can perform various malicious activities such as lateral movement, exfiltration, and persistence. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have access to the target host as user cyrano with password cyrano. From there, you can investigate the compromised system and any other reachable hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for any unauthorized or suspicious services running on the system.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check the running services and look for any that appear unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers to find how the service is set to start automatically.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Question:** What is the service name, filename, or destination host used for lateral movement?

**Hint:** Check the logs and systemd services for any indications of file transfers or remote execution.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through investigating the Linux.Bew backdoor malware, identifying its persistence mechanisms, and uncovering evidence of lateral movement. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and artifacts present in the provided data.