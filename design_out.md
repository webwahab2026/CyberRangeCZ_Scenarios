### Scenario: Rhombus Dropper Investigation

**INFO_LEVEL:**
The victim host in your network has been compromised by the Rhombus Linux DDoS botnet dropper. Your task is to investigate the compromise, identify the indicators of compromise (IOCs), and contain the threat. The malware is known to have persistence capabilities and communicates with a command and control (C2) server.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.120.10`.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer created by the malware.
**Description:** The Rhombus dropper is known to create a scheduled task for persistence. Investigate the systemd timers on the victim host to identify the suspicious timer.
**Hint:** Look for timers in the `/etc/systemd/system/` directory.
**Flag:** `session-mgr.timer`

**TRAINING_LEVEL 2:**
**Task:** Identify the hidden malware directory.
**Description:** The malware creates a hidden directory to store its components. Search the victim host for suspicious directories, especially in the `/tmp` directory.
**Hint:** Use the `ls` command with appropriate options to list hidden directories.
**Flag:** `/tmp/.session`

**TRAINING_LEVEL 3:**
**Task:** Identify the remote access trojan (RAT) component.
**Description:** The Rhombus dropper deploys a RAT component that communicates with the C2 server. Investigate the contents of the hidden malware directory to identify the RAT script.
**Hint:** Look for scripts in the hidden directory identified in the previous task.
**Flag:** `rat.sh`

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and containing the Rhombus dropper compromise. Each task is mapped to real hosts, services, and file paths derived from the sandbox environment.