# BlackTech PLEAD Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the BlackTech threat group using their PLEAD backdoor malware. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes that might indicate malware activity.

**Hint:** Check running services and processes for anything unusual or unauthorized.

**Validation:** The service name associated with the suspicious activity.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Hint:** Investigate systemd services and timers for any unusual configurations.

**Validation:** The service name or persistence identifier used for automatic startup.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Hint:** Correlate the suspicious service with files on disk to identify the malicious artifact.

**Validation:** The filename or file path of the malicious executable.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks focus on investigating and responding to the BlackTech PLEAD backdoor malware, with a defense-oriented approach suitable for an intermediate difficulty level. The scenario includes three training level tasks that guide the student through identifying suspicious services, determining persistence mechanisms, and locating malicious artifacts. Each task is validated based on the specific indicators or artifacts identified during the investigation.