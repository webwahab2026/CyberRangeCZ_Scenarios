### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The target system has been compromised by the BRICKSTORM backdoor malware. Your task is to investigate the compromise, identify indicators of compromise (IOCs), and contain the threat.

#### ACCESS_LEVEL
- **Entry Host**: target (IP: 192.168.50.5)
- **Username**: cyrano
- **Password**: cyrano

#### TRAINING_LEVEL 1
**Task**: Identify the suspicious service running on the target host.
**Description**: Investigate the running services on the target host and identify the suspicious service related to the BRICKSTORM backdoor.
**Hint**: Check the systemd services and look for any unusual or unfamiliar services.
**Flag**: updatemgr.service

#### TRAINING_LEVEL 2
**Task**: Identify the suspicious outbound IP address used for C2 communication.
**Description**: Analyze the network connections and logs on the target host to identify the suspicious outbound IP address used for command and control (C2) communication.
**Hint**: Check the network logs and connection history for any unusual IP addresses.
**Flag**: 192.168.40.5

#### TRAINING_LEVEL 3
**Task**: Identify the file transfer service used for lateral movement.
**Description**: Investigate the file transfer mechanisms on the target host to identify the service used for lateral movement to the next-target host.
**Hint**: Check the systemd services and logs for any file transfer activities.
**Flag**: payload-transfer.service

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and containing the BRICKSTORM backdoor malware.