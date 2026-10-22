Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I'll create a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario will focus on investigating and responding to the Linux/CDRThief malware targeting VoIP platforms.

---

### Scenario: VoIP Platform Compromise Investigation

**INFO_LEVEL:**
The organization has detected unusual network activity on its VoIP platform infrastructure. As an incident responder, your task is to investigate the compromised systems, identify the malware, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target VoIP platform server (target) with the username `cyrano` and password `cyrano`. From this server, you can investigate the compromise and access other connected systems as needed.

**TRAINING_LEVEL_1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the target VoIP platform server.
**Objective:** Enumerate running services and distinguish legitimate from suspicious services.
**Hint:** Check running services and look for any that seem out of place or unrelated to VoIP operations.
**Validation:** The service name should be identified and investigated.

**TRAINING_LEVEL_2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint:** Investigate system startup configurations and look for entries related to the suspicious service.
**Validation:** The persistence mechanism should be identified and described.

**TRAINING_LEVEL_3:**
**Task:** Locate the executable or file associated with the suspicious activity.
**Objective:** Correlate processes with files on disk and identify malicious artifacts.
**Hint:** Search for files related to the suspicious service and check their properties and contents.
**Validation:** The filename or file path should be identified and analyzed.

---

This scenario aligns with the provided MISP event describing the Linux/CDRThief malware, the security profile for incident response, and the sandbox environment defined by the topology and Ansible configuration. The tasks are designed to guide students through investigating and responding to the compromise while adhering to the constraints and requirements specified.