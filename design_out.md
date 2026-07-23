Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: BRICKSTORM Backdoor Investigation**

**INFO_LEVEL:**
The target network has been compromised by a sophisticated backdoor malware named BRICKSTORM. This malware uses advanced techniques to evade detection, including SOCKS proxying, multi-layered web service communication, and varied command execution. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. The target host's IP address is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target host.
**Question:** What is the name of the suspicious service running on the target host?
**Hint:** Check the running services and look for any that seem unusual or unauthorized.

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Question:** What is the persistence mechanism used by the suspicious service?
**Hint:** Investigate systemd services and timers to find how the service is started automatically.

**TRAINING_LEVEL 3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Question:** What is the path to the executable or file associated with the suspicious service?
**Hint:** Correlate the service with its associated files and look for any suspicious executables.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks are designed to guide students through the investigation and response process for the BRICKSTORM backdoor malware, focusing on service discovery, persistence mechanisms, and file investigation. The scenario uses only the hosts, services, and file paths that exist in the sandbox, ensuring realism and consistency.