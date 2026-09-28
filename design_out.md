### Scenario: Linux.Bew Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity, including unexpected outbound connections to an unknown server. Initial analysis suggests the presence of a backdoor that may be related to cryptocurrency mining. Your task is to investigate and mitigate this threat.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the `192.168.50.0/24` network.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target system.
**Question:** What is the name of the suspicious service running on the target system?
**Hint:** Check the list of running services and look for any that appear unusual or unauthorized.
**Answer:** bkd.service

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Question:** What is the persistence mechanism used by the suspicious service?
**Hint:** Investigate systemd services and timers to find how the service is scheduled to run.
**Answer:** systemd timer

**TRAINING_LEVEL 3:**
**Task:** Identify the process responsible for suspicious activity on the host.
**Question:** What is the name of the process responsible for the suspicious activity?
**Hint:** Analyze running processes and correlate them with the suspicious service.
**Answer:** lab-checkin.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through the investigation and mitigation of the Linux.Bew backdoor, focusing on identifying suspicious services, persistence mechanisms, and processes. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.