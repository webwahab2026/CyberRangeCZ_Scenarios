### Scenario: Sednit Dropper Investigation

#### INFO_LEVEL
The organization has detected suspicious activity on one of its internal servers. Initial analysis suggests a potential compromise involving a dropper associated with the Sednit group. Your task is to investigate the compromised host, identify the malware artifacts, and determine the extent of the compromise.

#### ACCESS_LEVEL
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is part of a network that includes a staging server and a command-and-control (C2) server. You can use standard Linux commands and tools to investigate the system.

#### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the compromised host.
**Description:** While reviewing the system services, you notice an unusual service that was not part of the standard configuration. Investigate this service to determine if it is related to the suspected compromise.
**Hint:** Check the list of running services and look for any that seem out of place or have unusual descriptions.
**Hidden Flag:** `session-mgr.service`

#### TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity.
**Description:** The system logs indicate that certain activities are occurring at regular intervals. Investigate the scheduled tasks or timers to identify any that might be related to the malware.
**Hint:** Look for timers or tasks that are set to run frequently and check their associated scripts or commands.
**Hidden Flag:** `session-mgr.timer`

#### TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.
**Description:** The malware is known to drop several files onto the system. Investigate the file system to identify any suspicious files that were created around the time of the suspected compromise.
**Hint:** Check directories that are not typically used for legitimate system files and look for files with unusual names or permissions.
**Hidden Flag:** `/tmp/.session/rat.sh`

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation process while ensuring they discover the required information through systematic analysis.