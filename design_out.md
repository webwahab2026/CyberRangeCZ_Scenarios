# Linux Coinminer Incident Response Scenario

## INFO_LEVEL
The organization has detected unusual CPU usage patterns on several Linux servers. Initial investigations suggest potential cryptocurrency mining activity. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the miner-host system with the username "cyrano" and password "cyrano". From this system, you can investigate the local host and potentially other connected systems.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual CPU usage on miner-host

**Description:**
You've noticed consistently high CPU usage on miner-host. Investigate this system to identify any unauthorized or suspicious services, processes, or network communications that might be causing this abnormal resource consumption.

**Hint:**
Check running services and processes, looking for anything unusual or unauthorized. Also examine network connections for suspicious outbound traffic.

**Validation:**
The systemd service name used for persistence must be identified.

## TRAINING_LEVEL 2
**Task:** Investigate potential lateral movement to second-host

**Description:**
Your investigation of miner-host revealed evidence of cryptocurrency mining activity. Now check if this malware has spread to other systems in the network. Specifically, investigate second-host for signs of compromise.

**Hint:**
Examine SSH logs and authentication records for evidence of unauthorized access or lateral movement.

**Validation:**
The SSH command used to spread the malware to second-host must be identified.

## TRAINING_LEVEL 3
**Task:** Contain and remediate the cryptomining activity

**Description:**
You've confirmed that both miner-host and second-host are compromised with cryptocurrency mining malware. Now contain and remediate this threat to prevent further resource consumption and potential spread.

**Hint:**
Consider terminating malicious processes, disabling persistence mechanisms, and removing malicious artifacts.

**Validation:**
The systemd service name that was disabled or removed must be identified.