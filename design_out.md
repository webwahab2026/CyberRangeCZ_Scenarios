### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Objective:**
Investigate and mitigate the BRICKSTORM backdoor malware on the target system. This malware uses advanced techniques for evasion, including SOCKS proxying, multi-layered web service communication, and varied command execution.

**Background:**
The BRICKSTORM backdoor has been detected on the target system. Your task is to investigate the malware's behavior, identify its persistence mechanisms, and mitigate the threat.

**Learning Objectives:**
- Understand the behavior of the BRICKSTORM backdoor malware.
- Identify and investigate suspicious services and files.
- Mitigate the threat by containing and removing the malware.

---

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious service related to the BRICKSTORM backdoor.

**Description:**
The BRICKSTORM backdoor uses a persistence mechanism through a systemd service. Investigate the systemd services on the target system to identify the suspicious service.

**Steps:**
1. SSH into the target system using the provided credentials.
2. List all systemd services and look for any suspicious services.
3. Identify the service related to the BRICKSTORM backdoor.

**Flag:** backdoor-persistence.service

**Hint:** Look for services that are not part of the standard system services.

---

#### TRAINING_LEVEL 2
**Task:** Investigate the suspicious file used by the BRICKSTORM backdoor.

**Description:**
The BRICKSTORM backdoor uses a backdoor binary for its operations. Investigate the file system to identify the suspicious file.

**Steps:**
1. SSH into the target system using the provided credentials.
2. Search the file system for suspicious files, especially in the `/usr/java/jre-vmware/bin` directory.
3. Identify the backdoor binary used by the BRICKSTORM malware.

**Flag:** /usr/java/jre-vmware/bin/updatemgr

**Hint:** Look for files that are not part of the standard system files.

---

#### TRAINING_LEVEL 3
**Task:** Mitigate the BRICKSTORM backdoor by removing its persistence mechanism.

**Description:**
The BRICKSTORM backdoor has a persistence mechanism through a systemd service. Remove the persistence mechanism to mitigate the threat.

**Steps:**
1. SSH into the target system using the provided credentials.
2. Stop and disable the suspicious systemd service identified in TRAINING_LEVEL 1.
3. Remove the backdoor binary identified in TRAINING_LEVEL 2.
4. Verify that the service and binary have been removed.

**Flag:** backdoor-persistence.service

**Hint:** Use systemd commands to stop and disable the service, and use file removal commands to delete the binary.

---

### Conclusion
By completing these tasks, you will have investigated and mitigated the BRICKSTORM backdoor malware on the target system. This exercise will help you understand the behavior of advanced malware and the steps needed to contain and remove such threats.