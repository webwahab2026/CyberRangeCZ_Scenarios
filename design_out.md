Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a BiBi-Linux Wiper malware incident.

### Scenario: BiBi-Linux Wiper Incident Response

**INFO_LEVEL:**
The corporate network has experienced a security incident involving data destruction. As an incident responder, your task is to investigate the affected systems, identify the cause of the data destruction, and contain the threat. The incident has affected both the workstation and file-server hosts in the corporate network.

**ACCESS_LEVEL:**
You have SSH access to the workstation host with the username `cyrano` and password `cyrano`. From there, you can investigate the local system and access the file-server host using SSH with the same credentials.

**TRAINING_LEVEL 1:**
**Task:** Identify evidence that files have been intentionally destroyed or rendered unusable.
**Description:** Investigate the workstation host to find evidence of file destruction. Look for unusual file modifications, missing files, or files with suspicious names. Pay attention to the `/data/company_files` directory and its subdirectories.
**Hint:** Check file modification times, file contents, and directory listings for anomalies.
**Validation:** The hidden flag is the name of a file that has been intentionally destroyed or rendered unusable.

**TRAINING_LEVEL 2:**
**Task:** Locate the executable or binary responsible for destructive activity.
**Description:** Search the workstation host for suspicious executables or binaries that might be responsible for the file destruction. Look for recently modified or created files in system directories, temporary directories, or user directories.
**Hint:** Check the contents of `/usr/local/sbin`, `/tmp`, and `/var/cache` for suspicious files.
**Validation:** The hidden flag is the path to the malware binary responsible for the destructive activity.

**TRAINING_LEVEL 3:**
**Task:** Determine how the malware is automatically executed after reboot or user logon.
**Description:** Investigate the workstation host to find persistence mechanisms that allow the malware to execute automatically. Look for scheduled tasks, services, or startup scripts that might be related to the malware.
**Hint:** Check systemd services, timers, and cron jobs for suspicious entries.
**Validation:** The hidden flag is the name of the persistence mechanism used by the malware.

---

This scenario is designed to be consistent with the provided sandbox environment, using only the hosts, services, and file paths that exist in the topology and Ansible configuration. The tasks are aligned with the NICE Incident Response profile and focus on investigating and responding to a wiper malware incident. The scenario encourages students to discover indicators through system, process, service, file system, and log analysis.