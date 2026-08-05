# XMRig Cryptominer Investigation

## INFO_LEVEL
The cybersecurity team has detected unusual CPU usage patterns on several Linux hosts in the network. Initial analysis suggests potential cryptocurrency mining activity. Your task is to investigate and contain this threat.

## ACCESS_LEVEL
You have SSH access to the miner-host system with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the unusual CPU usage on miner-host

**Description:**
The system administrator has reported consistently high CPU usage on miner-host. Your task is to identify the process responsible for this abnormal resource consumption.

**Hint:**
Check running processes and their resource utilization.

**Validation:**
The correct process name is sys-monitor

## TRAINING_LEVEL 2
**Task:** Locate the executable associated with the suspicious process

**Description:**
After identifying the suspicious process, locate the executable file responsible for this activity. This will help you understand how the malware is operating on the system.

**Hint:**
Search for the process name in common executable directories.

**Validation:**
The correct file path is /usr/local/sbin/sys-monitor

## TRAINING_LEVEL 3
**Task:** Identify the external communication destination

**Description:**
Determine where the suspicious process is sending network traffic. This will help you understand the command and control infrastructure supporting this cryptomining activity.

**Hint:**
Examine active network connections and their destinations.

**Validation:**
The correct destination is pool-server:3333