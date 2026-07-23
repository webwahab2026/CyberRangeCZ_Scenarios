### Scenario: Coinminer Incident Response

**INFO_LEVEL:**
This scenario simulates an incident involving a Coinminer malware infection on Linux servers. The malware utilizes CPU and GPU resources to mine cryptocurrencies without authorization. Your task is to investigate, analyze, and respond to this security incident.

**ACCESS_LEVEL:**
- Entry Host: miner-host
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service causing abnormal CPU usage.
**Description:** Investigate the miner-host for any suspicious services that might be causing high CPU usage. Look for services that are not part of the standard system processes.
**Hint:** Check the systemd services and look for any unusual service names or descriptions.
**Flag:** sys-monitor

**TRAINING_LEVEL 2:**
**Task:** Identify the malware dropper artifact.
**Description:** Examine the miner-host for any suspicious files that might have been used to drop the malware. Look for scripts or binaries in unusual locations.
**Hint:** Check the /tmp directory for any suspicious files.
**Flag:** /tmp/hsos

**TRAINING_LEVEL 3:**
**Task:** Identify the persistence mechanism through a system service.
**Description:** Investigate the miner-host for any persistence mechanisms that the malware might have implemented. Look for system services that are set to start automatically and might be related to the malware.
**Hint:** Check the systemd services and look for any services that are set to start automatically and might be related to the malware.
**Flag:** sys-monitor.service