### Scenario: Coinminer Incident Response

**INFO_LEVEL:**
The cyber range environment contains a compromised Linux server (miner-host) infected with a coinminer malware. The malware has spread to another host (second-host) within the network. Your task is to investigate, analyze, and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: miner-host
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service installed by the attacker.
**Description:** The attacker has installed a malicious service on the system. Investigate the system services and identify the suspicious service.
**Hint:** Check the systemd service files in the /etc/systemd/system directory.
**Flag:** sys-monitor.service

**TRAINING_LEVEL 2:**
**Task:** Identify the malware configuration file.
**Description:** The malware uses a configuration file to operate. Locate and identify this configuration file.
**Hint:** Check the .config directory in the home folder of the user cyrano.
**Flag:** /home/cyrano/.config/sys-monitor/config.json

**TRAINING_LEVEL 3:**
**Task:** Identify the persistence mechanism through a system service.
**Description:** The malware has implemented a persistence mechanism using a system service. Identify the service responsible for this persistence.
**Hint:** Check the systemd service files in the /etc/systemd/system directory.
**Flag:** sys-monitor.service

**Q/A:**
1. What is the name of the suspicious service installed by the attacker?
   - Answer: sys-monitor.service

2. What is the path to the malware configuration file?
   - Answer: /home/cyrano/.config/sys-monitor/config.json

3. What is the name of the system service used for persistence?
   - Answer: sys-monitor.service

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.