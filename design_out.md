# KYPO Scenario: Linux Coinminer Investigation

## INFO_LEVEL
The network has experienced unusual CPU usage patterns on multiple hosts. Your task is to investigate and identify the source of this activity.

## ACCESS_LEVEL
You have SSH access to the following hosts:
- miner-host (IP: 192.168.50.5)
- second-host (IP: 192.168.50.6)

Use the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on miner-host that is consuming excessive CPU resources.

**Hint:** Check the systemd services and look for any unusual or unauthorized services.

**Validation:**
- The student must identify the service name "sys-monitor" running on miner-host.

## TRAINING_LEVEL 2
**Task:** Analyze the process responsible for the abnormal CPU usage on miner-host.

**Hint:** Use process monitoring tools to identify the process consuming the most CPU resources.

**Validation:**
- The student must identify the process name "/usr/local/sbin/python" running on miner-host.

## TRAINING_LEVEL 3
**Task:** Locate the executable file associated with the suspicious activity on miner-host.

**Hint:** Investigate the file system for any unusual or recently modified executables.

**Validation:**
- The student must identify the file path "/usr/local/sbin/python" on miner-host.