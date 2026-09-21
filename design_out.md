### Scenario: Groundhog Backdoor Investigation

**INFO_LEVEL:**
The Groundhog backdoor malware has been detected in your network. This malware targets Linux servers, uses XOR encryption for communication, and can perform DDoS attacks. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can access the `next-target` host using SSH.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Question:** What is the name of the suspicious service running on the `target` host?
**Hint:** Check the running services and look for any that seem unusual or unauthorized.
**Answer:** bkd.service

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Question:** What is the persistence mechanism used by the suspicious service?
**Hint:** Investigate the systemd services and timers to find how the service is started.
**Answer:** systemd timer

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Question:** What is the path to the script that the suspicious service executes?
**Hint:** Check the service unit file for the executable path.
**Answer:** /usr/local/bin/lab-checkin.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through investigating the Groundhog backdoor malware, identifying its persistence mechanisms, and locating associated files. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.