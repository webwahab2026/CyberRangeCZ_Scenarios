### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The BRICKSTORM backdoor is a sophisticated 64-bit ELF executable written in Go, targeting Linux systems. It employs advanced evasion techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution. The backdoor uses DoH, nested TLS encryption, and abuses a legitimate cloud service to evade detection. It is capable of C2 communication, lateral movement, exfiltration, and persistence.

#### ACCESS_LEVEL
- **Entry Host**: target (IP: 192.168.50.5)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

#### TRAINING_LEVEL 1
**Task**: Identify and investigate the suspicious service running on the target host.
**Description**: The target host is exhibiting unusual network behavior. Investigate the running services to identify any suspicious activity.
**Hint**: Check the systemd services and look for any unusual or unfamiliar services.
**Flag**: vmware-sphere.service

#### TRAINING_LEVEL 2
**Task**: Identify the suspicious outbound IP and port used for C2 communication.
**Description**: The BRICKSTORM backdoor is communicating with a C2 server. Identify the IP address and port used for this communication.
**Hint**: Check the network connections and logs for any suspicious outbound connections.
**Flag**: 192.168.40.5:4444

#### TRAINING_LEVEL 3
**Task**: Investigate the file transfer mechanism used for lateral movement.
**Description**: The BRICKSTORM backdoor is transferring files between hosts for lateral movement. Identify the service responsible for this activity.
**Hint**: Check the systemd services and logs for any file transfer activities.
**Flag**: payload-transfer.service

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the user through identifying and investigating the BRICKSTORM backdoor's activities, focusing on service identification, C2 communication, and lateral movement mechanisms.