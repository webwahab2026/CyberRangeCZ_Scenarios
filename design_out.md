# Scenario: BRICKSTORM Backdoor Investigation

## INFO_LEVEL

This scenario involves investigating a compromised system infected with the BRICKSTORM backdoor. The backdoor is a Go-based malware that uses advanced evasion techniques including DoH, nested TLS encryption, and abuse of legitimate cloud services. It employs SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. The backdoor uses XOR cipher encryption to hide key strings and implements self-preservation mechanisms through environment variable checks and process reinstallation.

The malware has established persistence on the target system and is communicating with a Command and Control (C2) server. It also demonstrates lateral movement capabilities to a secondary target system. The investigation should focus on identifying the backdoor's presence, understanding its communication patterns, and determining how to contain and remove the threat.

## ACCESS_LEVEL

Access to the target system is provided through SSH using the user `cyrano` with password `cyrano`. The target system has sudo privileges. The investigation should be conducted from the target system, with access to both the target and next-target systems for lateral movement analysis.

## TRAINING_LEVEL

### Task 1: Identify suspicious service persistence mechanism

**Objective:** Identify the service that maintains persistence for the BRICKSTORM backdoor.

**Instructions:** 
1. Investigate running services on the target system
2. Look for services related to the BRICKSTORM backdoor
3. Identify the service name that maintains persistence

**Flag:** `bricks.service`

**Hint:** Look for services that start with "bricks" in the systemd service configuration.

**Question:** What is the name of the systemd service that maintains BRICKSTORM backdoor persistence?

### Task 2: Identify suspicious outbound communication

**Objective:** Identify the C2 communication pattern used by the BRICKSTORM backdoor.

**Instructions:**
1. Examine network connections and listening ports on the target system
2. Look for outbound connections to the C2 server
3. Identify the DoH communication mechanism used by the backdoor

**Flag:** `8.8.8.8`

**Hint:** Check for DNS queries to common DoH servers in the system logs.

**Question:** Which DoH server IP address was used by the BRICKSTORM backdoor for C2 communication?

### Task 3: Identify file transfer between hosts for lateral movement

**Objective:** Identify the service responsible for lateral movement between the target and next-target systems.

**Instructions:**
1. Investigate running services on the target system
2. Look for services that perform file transfers between systems
3. Identify the service name responsible for lateral movement

**Flag:** `payload-transfer.service`

**Hint:** Look for services that perform periodic data synchronization between hosts.

**Question:** What is the name of the service that facilitates file transfer between the target and next-target systems?