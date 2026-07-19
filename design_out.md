# Scenario: BRICKSTORM Incident Response

## INFO_LEVEL

This scenario involves investigating a BRICKSTORM backdoor infection on a target system. The malware is a Go-based backdoor that uses advanced evasion techniques including DoH, nested TLS encryption, and abuse of legitimate cloud services. It employs SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. The backdoor uses XOR cipher encryption to hide key strings and implements self-preservation mechanisms through environment variable checks and process reinstallation. The malware exhibits C2 communication, lateral movement, data exfiltration, and persistence capabilities.

## ACCESS_LEVEL

Access to the target system is provided via SSH using the user `cyrano` with password `cyrano`. The target system has a user `cyrano` with sudo privileges. The target system can also communicate with the next-target system via SSH. The C2 server is accessible from the target system.

## TRAINING_LEVEL

### Task 1: Identify suspicious outbound communication

**Task Description:**  
Investigate the target system for suspicious outbound network connections that may indicate C2 communication. Identify the port and destination IP address used by the malware for C2 communication.

**Flag:** C2 Port address

**Hint:**  
Check the system logs for outbound connections to the C2 server. Look for connections on port 4444.

**Question:**  
What is the port number used by the malware for C2 communication?

**Answer:**  
4444

### Task 2: Identify file transfer between hosts for lateral movement

**Task Description:**  
Investigate the target system for evidence of lateral movement. Identify the service responsible for transferring data between the target and next-target systems.

**Flag:** Service name

**Hint:**  
Look for services that are running and responsible for data synchronization between hosts. Check systemd services.

**Question:**  
What is the name of the service responsible for lateral movement between the target and next-target systems?

**Answer:**  
payload-transfer.service

### Task 3: Identify persistence mechanism

**Task Description:**  
Investigate the target system for persistence mechanisms implemented by the malware. Identify the service responsible for maintaining persistence on the system.

**Flag:** Service name

**Hint:**  
Check for services that are configured to start automatically on system boot. Look for services related to periodic check-ins.

**Question:**  
What is the name of the service that maintains persistence on the target system?

**Answer:**  
lab-checkin.service