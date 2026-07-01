### Scenario: Mirai Worm Investigation

**INFO_LEVEL:**
The Mirai worm is a well-known malware that targets Linux systems, particularly IoT devices. It propagates by exploiting vulnerabilities and uses compromised devices to launch distributed denial-of-service (DDoS) attacks. In this scenario, you will investigate an infection of the Mirai worm within a controlled network environment. Your goal is to identify the extent of the infection, understand the propagation mechanism, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the `patient-zero` host with the username `cyrano` and password `cyrano`. From this host, you can investigate the infection and access other compromised hosts within the network.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer used by the malware for persistence.
**Description:** The Mirai worm uses a scheduled task to maintain persistence on infected hosts. Investigate the systemd timers on the `patient-zero` host to identify the malicious timer.
**Hint:** Look for timers in the `/etc/systemd/system/` directory.
**Flag:** sysnet-monitor.timer

**TRAINING_LEVEL 2:**
**Task:** Identify the hidden malware directory used by the worm.
**Description:** The Mirai worm creates a hidden directory to store its files. Investigate the file system on the `patient-zero` host to locate this directory.
**Hint:** Check directories in `/opt/` for suspicious names.
**Flag:** /opt/.worm

**TRAINING_LEVEL 3:**
**Task:** Identify the compromised host discovered through propagation logs.
**Description:** The Mirai worm logs its propagation activities. Investigate the spread log on the `patient-zero` host to identify a compromised host.
**Hint:** Check the spread log located in the hidden malware directory.
**Flag:** 192.168.90.10