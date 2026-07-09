### Scenario: PACHA Malware Investigation

#### INFO_LEVEL
The PACHA malware is a Linux server infection that uses coinminers and employs various techniques for persistence, exfiltration, and command and control (C2) communication. Your task is to investigate and respond to this malware infection on the target systems.

#### ACCESS_LEVEL
- **Entry Host**: target
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

#### TRAINING_LEVEL 1
**Task**: Identify and investigate the suspicious service that is part of the PACHA malware infection.
**Description**: The PACHA malware uses a service for its malicious activities. Investigate the target host to identify this suspicious service.
**Hint**: Check the systemd services running on the target host.
**Flag**: payload-transfer.service

#### TRAINING_LEVEL 2
**Task**: Identify and investigate the data exfiltration mechanism used by the PACHA malware.
**Description**: The PACHA malware exfiltrates data from the infected host. Investigate the target host to identify the file used for data exfiltration.
**Hint**: Check the logs and files in the home directory of the user cyrano.
**Flag**: payload-transfer.log

#### TRAINING_LEVEL 3
**Task**: Contain the C2 communication by blocking the suspicious outbound port.
**Description**: The PACHA malware communicates with a C2 server using a specific port. Identify and block this port to contain the malware's activities.
**Hint**: Check the network connections and open ports on the target host.
**Flag**: 8080

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the user through investigating and responding to the PACHA malware infection, focusing on identifying suspicious services, data exfiltration mechanisms, and containing C2 communication.