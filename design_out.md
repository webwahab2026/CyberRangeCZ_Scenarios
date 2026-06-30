### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The target system has been compromised by the BRICKSTORM backdoor malware. Your task is to investigate the compromise, identify indicators of compromise (IOCs), and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

#### TRAINING_LEVEL 1
**Task:** Identify and investigate the suspicious service running on the target system.

**Description:**
The target system is running a suspicious service that might be related to the BRICKSTORM backdoor. Investigate the service and identify its name.

**Hint:**
Check the running services on the target system.

**Flag:**
The flag is the name of the suspicious service.

#### TRAINING_LEVEL 2
**Task:** Identify and investigate the suspicious outbound IP address.

**Description:**
The BRICKSTORM backdoor communicates with a command and control (C2) server. Identify the suspicious outbound IP address that the backdoor is communicating with.

**Hint:**
Check the network connections on the target system.

**Flag:**
The flag is the C2 IP address in the sandbox.

#### TRAINING_LEVEL 3
**Task:** Contain the C2 communication.

**Description:**
To prevent further communication with the C2 server, you need to block the outbound connection to the identified C2 IP address and port.

**Hint:**
Use firewall rules to block the outbound connection.

**Flag:**
The flag is the port number used for C2 communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through identifying, investigating, and containing the BRICKSTORM backdoor malware.