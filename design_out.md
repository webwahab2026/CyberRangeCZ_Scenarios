# Rakos Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Rakos backdoor malware. This malware spreads via brute force SSH attacks and establishes command-and-control (C2) communication. Your task is to investigate the compromised hosts, identify the malware's activities, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for any unauthorized or suspicious services running on the system.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the systemd service unit file responsible for the persistence of the suspicious service?

**Hint:** Examine the systemd service files and look for any that are related to the suspicious service identified in the previous task.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Question:** What is the name of the service responsible for transferring files from the target host to the next-target host?

**Hint:** Investigate the systemd services and look for any that involve file transfers or remote execution.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Rakos backdoor malware, focusing on service discovery, persistence mechanisms, and lateral movement. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.