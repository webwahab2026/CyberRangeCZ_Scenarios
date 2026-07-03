### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Objective:**
Investigate and respond to a BRICKSTORM backdoor infection on the target network. The BRICKSTORM malware is a sophisticated 64-bit ELF executable written in Go, known for its advanced evasion techniques including SOCKS proxying, multi-layered web service communication, and varied command execution.

**Background:**
The security team has detected suspicious activity on the target network. Your task is to investigate the compromised host, identify the malware, and take appropriate containment measures.

**Learning Objectives:**
- Identify and investigate suspicious services and files.
- Analyze network traffic for signs of command and control (C2) communication.
- Contain and mitigate the threat posed by the BRICKSTORM backdoor.

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service
**Description:**
Investigate the target host for suspicious services. The BRICKSTORM backdoor is known to use SOCKS proxying and multi-layered web service communication. Identify any unusual services running on the host.

**Hint:**
Check the list of running services and look for any that appear suspicious or unusual.

**Flag:**
service name

#### TRAINING_LEVEL 2
**Task:** Investigate Suspicious File
**Description:**
Examine the target host for suspicious files. The BRICKSTORM backdoor is a 64-bit ELF executable written in Go. Look for any unusual files that match this description.

**Hint:**
Search for files with unusual names or properties that match the description of the BRICKSTORM backdoor.

**Flag:**
file name

#### TRAINING_LEVEL 3
**Task:** Contain C2 Communication
**Description:**
Identify and block any outbound communication to known command and control (C2) servers. The BRICKSTORM backdoor uses HTTPS and WebSocket addresses for C2 communication. Block the port used for this communication to contain the threat.

**Hint:**
Check network connections and block the port used for C2 communication.

**Flag:**
Port number

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and relies on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The scenario adheres to the strict MISP constraints and prioritizes the use of indicators explicitly present in the MISP event.