# Rakos Malware Investigation

## INFO_LEVEL
The Rakos malware is a Linux backdoor that performs brute force SSH login attempts to compromise devices and servers with weak passwords. It aims to assemble a list of unsecured devices to create a botnet. The malware is written in Go and typically compressed with UPX. It has capabilities for updating its configuration and upgrading itself.

## ACCESS_LEVEL
You have access to the target host with the username `cyrano` and password `cyrano`. From this host, you can investigate the system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for any unauthorized or suspicious services running.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check the running services and look for any that seem unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers to find how the service is started automatically.

## TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.

**Question:** What is the service name, filename, or destination host used for lateral movement?

**Hint:** Check the system logs and network connections for evidence of lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Rakos malware, focusing on service discovery, persistence mechanisms, and lateral movement. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and artifacts present in the provided data.