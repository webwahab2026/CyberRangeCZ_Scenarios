# BiBi-Linux Wiper Incident Response Scenario

## INFO_LEVEL
The company has detected unusual activity on its internal systems. Initial reports indicate that critical files have been destroyed or corrupted. Your task is to investigate the incident, identify the cause, and assess the impact.

## ACCESS_LEVEL
You have SSH access to the workstation host with the username `cyrano` and password `cyrano`. From there, you can investigate the system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Identify evidence that files have been intentionally destroyed or rendered unusable.

**Description:**
Investigate the workstation host and look for signs of file destruction. Pay attention to file modifications, unusual filenames, and any indicators of malicious activity.

**Hint:**
Check the contents of the `/data/company_files` directory and look for any files that have been modified or renamed in an unusual way.

**Validation:**
The hidden flag is the name of a file that has been renamed as part of the destructive activity.

## TRAINING_LEVEL 2
**Task:** Locate the executable or binary responsible for the destructive activity.

**Description:**
Search the workstation host for any suspicious executables or binaries that might be responsible for the file destruction. Look for recently modified files, unusual file paths, or files with suspicious permissions.

**Hint:**
Check the `/usr/local/sbin` directory for any recently modified executables.

**Validation:**
The hidden flag is the name of the malware binary responsible for the destructive activity.

## TRAINING_LEVEL 3
**Task:** Determine how the malware is automatically executed after reboot or user logon.

**Description:**
Investigate the workstation host for any persistence mechanisms that might be responsible for automatically executing the malware. Look for scheduled tasks, services, or startup scripts that could trigger the malware.

**Hint:**
Check the contents of the `/etc/systemd/system` directory for any suspicious services or timers.

**Validation:**
The hidden flag is the name of the service or timer responsible for the malware's persistence.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a BiBi-Linux Wiper incident, focusing on identifying file destruction, locating the malware binary, and determining its persistence mechanism. The scenario emphasizes realistic investigation techniques and encourages students to discover indicators through system and log analysis.