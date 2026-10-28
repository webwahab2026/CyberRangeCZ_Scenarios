# Coinminer Incident Response Scenario

## INFO_LEVEL
The IT department has detected unusual CPU usage on several Linux servers in the network. Initial investigation suggests the presence of cryptocurrency mining malware. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- `miner-host` (192.168.50.5)
- `second-host` (192.168.50.6)
- `pool-server` (192.168.40.5)

## TRAINING_LEVEL 1
**Task:** Investigate the unusual CPU usage on `miner-host`

**Description:**
The system administrator has noticed consistently high CPU usage on `miner-host`. Investigate this host to identify any suspicious processes or services that might be causing this abnormal behavior.

**Hint:**
Check running processes and services for anything unusual or unauthorized.

**Validation:**
The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Analyze network connections on `miner-host`

**Description:**
After identifying suspicious processes, examine the network connections on `miner-host` to determine if the system is communicating with any external hosts that might be related to cryptocurrency mining.

**Hint:**
Look for unusual outbound connections, especially to ports commonly used for mining pools.

**Validation:**
The hidden flag is the port number used for suspicious outbound communication.

## TRAINING_LEVEL 3
**Task:** Investigate lateral movement to `second-host`

**Description:**
Examine `second-host` to determine if the cryptocurrency mining malware has spread from `miner-host`. Identify any evidence of lateral movement or unauthorized access.

**Hint:**
Check for any unusual files, services, or network connections that might indicate lateral movement.

**Validation:**
The hidden flag is the name of the script or tool used to propagate the malware to `second-host`.