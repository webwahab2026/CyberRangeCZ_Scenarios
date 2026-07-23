### Scenario: Mirai Worm Investigation

**INFO_LEVEL:**
The Mirai worm is a well-known malware that targets Linux-based IoT devices. It scans for devices using default credentials and exploits them to create a botnet. In this scenario, you will investigate a network compromised by a variant of the Mirai worm named Linux/Mirai.Y!tr.bdr. Your goal is to identify the infection, understand its behavior, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the patient-zero host with the username `cyrano` and password `cyrano`. From there, you can investigate the network and other compromised hosts.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer created by the malware.
**Description:** The Mirai worm creates a scheduled task to maintain persistence. Investigate the systemd timers on the patient-zero host to find the suspicious timer.
**Hint:** Look for timers in the `/etc/systemd/system/` directory.
**Flag:** sysnet-monitor.timer

**TRAINING_LEVEL 2:**
**Task:** Identify the hidden malware directory.
**Description:** The Mirai worm creates a hidden directory to store its files. Search the filesystem on the patient-zero host to find this directory.
**Hint:** Check directories that are not typically used by the system.
**Flag:** /opt/.worm

**TRAINING_LEVEL 3:**
**Task:** Identify the beaconing mechanism used by the malware.
**Description:** The Mirai worm communicates with a command and control (C2) server. Investigate the scripts in the hidden malware directory to find the beaconing mechanism.
**Hint:** Look for scripts that make network connections to the attacker host.
**Flag:** /opt/.worm/beacon.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through identifying and containing the Mirai worm infection.