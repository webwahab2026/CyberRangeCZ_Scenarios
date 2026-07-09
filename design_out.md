### Scenario: Mirai Worm Investigation

**INFO_LEVEL:**
The Mirai worm is a well-known malware that turns networked devices running Linux into remotely controlled bots. It primarily targets online consumer devices such as IP cameras and home routers. The malware continuously scans the internet for vulnerable IoT devices using a table of common factory default usernames and passwords. In this scenario, you will investigate a network compromised by the Mirai worm and perform incident response tasks to contain and analyze the infection.

**ACCESS_LEVEL:**
You have SSH access to the `patient-zero` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised network and perform necessary actions to contain the infection.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer used by the malware for persistence.
**Description:** The Mirai worm uses a scheduled task to maintain persistence on infected hosts. Investigate the systemd timers on the `patient-zero` host to identify the suspicious timer.
**Hint:** Look for timers in the `/etc/systemd/system/` directory.
**Flag:** sysnet-monitor.timer

**TRAINING_LEVEL 2:**
**Task:** Identify the hidden malware directory used by the worm.
**Description:** The Mirai worm creates a hidden directory to store its files. Investigate the filesystem on the `patient-zero` host to find this directory.
**Hint:** Check directories in `/opt/` for suspicious names.
**Flag:** /opt/.worm

**TRAINING_LEVEL 3:**
**Task:** Identify the beaconing mechanism used by the worm to communicate with the command and control (C2) server.
**Description:** The Mirai worm uses a beaconing mechanism to communicate with its C2 server. Investigate the scripts in the hidden malware directory on the `patient-zero` host to identify the beaconing script.
**Hint:** Look for scripts in the hidden malware directory that make network connections.
**Flag:** /opt/.worm/beacon.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and containing the Mirai worm infection, using only the indicators and artifacts present in the sandbox environment.