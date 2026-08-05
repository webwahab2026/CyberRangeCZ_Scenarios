Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a BiBi-Linux Wiper malware incident.

### Scenario: BiBi-Linux Wiper Incident Response

#### INFO_LEVEL
The corporate network has experienced a security incident involving data destruction. As an incident responder, your task is to investigate the affected systems, identify the cause of the incident, and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the workstation (192.168.50.5) as user 'cyrano' with password 'cyrano'. From there, you can investigate the system and access other network resources as needed.

#### TRAINING_LEVEL 1
**Task:** Identify evidence that files have been intentionally destroyed or rendered unusable.
**Description:** Investigate the workstation for signs of file destruction. Look for unusual file modifications, missing files, or other indicators that files have been intentionally destroyed.
**Hint:** Check the contents of the /data/company_files directory and look for unusual file names or modifications.
**Validation:** The hidden flag is the name of a file that has been renamed as part of the destructive activity.

#### TRAINING_LEVEL 2
**Task:** Locate the executable or binary responsible for destructive activity.
**Description:** Search the workstation for suspicious executables or binaries that might be responsible for the file destruction. Pay attention to unusual file locations, permissions, or timestamps.
**Hint:** Check the /usr/local/sbin directory for suspicious files.
**Validation:** The hidden flag is the name of the malware binary responsible for the destructive activity.

#### TRAINING_LEVEL 3
**Task:** Determine how the malware is automatically executed after reboot or user logon.
**Description:** Investigate the workstation for persistence mechanisms that might be used to automatically execute the malware. Look for scheduled tasks, services, or other methods of ensuring the malware runs automatically.
**Hint:** Check the contents of the /etc/systemd/system directory for suspicious service or timer files.
**Validation:** The hidden flag is the name of the systemd service or timer responsible for the malware's persistence.

---

This scenario is designed to be consistent with the provided sandbox environment, using only the hosts, services, and file paths that exist in the topology and Ansible data. The tasks are aligned with the MISP event describing the BiBi-Linux Wiper malware and the security profile for incident response. The scenario encourages students to investigate and discover the required information through analysis rather than being told where to look.