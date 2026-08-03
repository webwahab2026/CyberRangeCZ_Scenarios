# XMrig Cryptominer Investigation

## INFO_LEVEL
The network has experienced unusual CPU and network activity. Your task is to investigate and identify the source of this activity, determine if it's malicious, and take appropriate action.

## ACCESS_LEVEL
You have SSH access to the miner-host system with the username `cyrano` and password `cyrano`. From this system, you can investigate the host and potentially other connected systems.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual CPU usage on miner-host

**Description:**
The system administrator has noticed consistently high CPU usage on miner-host. Investigate this host to identify any unauthorized or suspicious services that might be causing this issue.

**Hint:**
Check running services and processes to identify any unusual activity.

**Validation:**
The service name is `sys-monitor`.

## TRAINING_LEVEL 2
**Task:** Investigate the suspicious process responsible for high CPU usage

**Description:**
You've identified a suspicious service running on miner-host. Now, investigate the process associated with this service to understand its behavior and resource consumption.

**Hint:**
Examine running processes and their resource usage to identify the malicious process.

**Validation:**
The process name is `dash`.

## TRAINING_LEVEL 3
**Task:** Identify the malicious artifact responsible for the cryptomining activity

**Description:**
You've identified a suspicious process running on miner-host. Now, locate the executable or file associated with this process to understand how it was deployed and maintained.

**Hint:**
Search for unusual files in system directories and investigate their properties.

**Validation:**
The filename is `/usr/local/sbin/dash`.