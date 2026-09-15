# Sednit Dropper Investigation

## INFO_LEVEL
The victim host in your network has exhibited suspicious behavior. Your task is to investigate the compromise, identify the malware, and determine the extent of the intrusion.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services running on the system.

**Question:** What is the name of the suspicious service responsible for maintaining unauthorized access to the system?

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity.

**Question:** What is the name of the timer responsible for the periodic execution of the suspicious service?

**Hint:** Examine the systemd timers to identify any that might be related to the suspicious service.

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Question:** What is the name of the directory created to conceal malicious files or payloads?

**Hint:** Investigate unusual or hidden directories that might contain suspicious files.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Sednit dropper malware, identifying its persistence mechanisms, and uncovering its artifacts on the victim host. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.