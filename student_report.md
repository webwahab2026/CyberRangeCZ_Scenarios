# BiBi-Linux Wiper Incident Response — Student Briefing

## 1. Malware Overview
- **Family / type**: Wiper
- **Aliases**: BiBi-Linux Wiper
- **Behaviour class**: Destructive malware

The BiBi-Linux Wiper is a Linux-based wiper malware used by pro-Hamas hacktivists to target Israeli entities. It is an x64 ELF executable written in C/C++ and compiled using the GCC compiler. The malware lacks obfuscation or protective measures and can destroy an entire operating system when run with root permissions. It overwrites files, renames them with a random string containing 'BiBi', and excludes certain file types from corruption. The malware does not drop a ransom note and does not use C2 servers, indicating its sole purpose is data destruction.

**Associated MITRE ATT&CK techniques**:
- [T1485](https://attack.mitre.org/techniques/T1485) - Data Destruction
- [T1562](https://attack.mitre.org/techniques/T1562) - Impair Defenses
- [T1059](https://attack.mitre.org/techniques/T1059) - Command-Line Interface

## 2. Exercise Objective
The learning goal of this cyber-range exercise is to investigate the compromised workstation, identify the malware's activities, and take appropriate measures to contain and remediate the threat.

- **Difficulty level**: Intermediate
- **Cybersecurity approach**: Defence-oriented
- **NICE work role**: Incident Response

By the end of this exercise, a successful trainee will have demonstrated the ability to investigate and identify running services and their behaviors, analyze network communication to detect unauthorized activities, discover and remove persistence mechanisms, investigate lateral movement and unauthorized file transfers, and identify the initial compromise vector and remediate the system.

## 3. Sandbox Topology & Malware Emulation
The sandbox topology consists of the following hosts and networks:

```
attacker-switch (192.168.40.0/24)
│
├── attacker (192.168.40.5)
│
router (192.168.40.1 / 192.168.50.1)
│
corp-switch (192.168.50.0/24)
    ├── workstation (192.168.50.5)
    └── file-server (192.168.50.6)
```

The malware behaviour is emulated as follows:

- **Service**: `bibi-linux.service` (emulates the wiper malware)
  - **Location**: `/usr/local/sbin/disk-maintenance`
  - **Description**: A script that enumerates, zeroes, and renames files in `/data/company_files`
  - **Network Port**: `4444` (used for communication with the attacker)
  - **Persistence Mechanism**: `bibi-linux.timer` (ensures the service runs across reboots)

## 4. Student Tasks
### ACCESS Step
- **Credentials**: Username: `cyrano`, Password: `cyrano`
- **Start Passkey**: `start`

### TRAINING_LEVEL 1: Identify Suspicious Service
- **Task**: Investigate the running services and identify the service responsible for the suspicious activity that enumerated, zeroed, and renamed the company files on the workstation.
- **Expected Artifact Type**: Service name

### TRAINING_LEVEL 2: Determine Network Port
- **Task**: Investigate the service and determine the network port associated with this communication.
- **Expected Artifact Type**: Network port number

### TRAINING_LEVEL 3: Identify Persistence Mechanism
- **Task**: Determine which system component is responsible for keeping the `bibi-linux.service` running across reboots and process termination.
- **Expected Artifact Type**: Timer name

## 5. Solution Walkthrough & Flags
### TRAINING_LEVEL 1: Identify Suspicious Service
1. **List all services**:
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services**:
   Look for services with unusual names or descriptions. Pay attention to services that might be related to disk maintenance or storage cleanup.
3. **Check the status of suspicious services**:
   ```bash
   systemctl status <service_name>
   ```
4. **Inspect the service configuration**:
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the service responsible for the suspicious activity**:
   The service name is `bibi-linux.service`.

**Flag**: `bibi-linux.service`

### TRAINING_LEVEL 2: Determine Network Port
1. **Inspect the service configuration**:
   ```bash
   systemctl cat bibi-linux.service
   ```
2. **Identify the ExecStart command**:
   Look for the path to the script launched by the service.
3. **Inspect the script**:
   ```bash
   cat /usr/local/sbin/disk-maintenance
   ```
4. **Identify the network port**:
   The port number is `4444`.

**Flag**: `4444`

### TRAINING_LEVEL 3: Identify Persistence Mechanism
1. **List all timers**:
   ```bash
   systemctl list-timers --all
   ```
2. **Identify the timer associated with the service**:
   Look for timers with names related to `bibi-linux.service`.
3. **Inspect the timer configuration**:
   ```bash
   systemctl cat bibi-linux.timer
   ```
4. **Identify the timer responsible for the persistence**:
   The timer name is `bibi-linux.timer`.

**Flag**: `bibi-linux.timer`

## 6. Knowledge Gained
- **Skills**:
  - Investigating and identifying running services and their behaviors.
  - Analyzing network communication to detect unauthorized activities.
  - Discovering and removing persistence mechanisms.
  - Investigating lateral movement and unauthorized file transfers.
  - Identifying the initial compromise vector and remediating the system.
- **Tools**:
  - `systemctl` for managing and inspecting services and timers.
  - `cat` for inspecting script contents.
- **Concepts**:
  - Service and timer management in Linux.
  - Network port identification.
  - Persistence mechanisms in malware.
- **NICE Role**: Incident Response
- **MITRE Techniques**:
  - [T1485](https://attack.mitre.org/techniques/T1485) - Data Destruction
  - [T1562](https://attack.mitre.org/techniques/T1562) - Impair Defenses
  - [T1059](https://attack.mitre.org/techniques/T1059) - Command-Line Interface
