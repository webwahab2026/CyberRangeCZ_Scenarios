Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Earth Lusca Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Earth Lusca malware family, specifically the KTLVdoor backdoor. Your team has been tasked with investigating and responding to this potential compromise.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you've noticed unusual outbound connections from the target host. Investigate this activity to identify any suspicious services or processes that might be responsible.

**Hint:**
Check running services and network connections to identify any unusual activity.

**Validation:**
The system should validate that the student has identified the suspicious service running on port 443.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate startup mechanisms and configuration files to understand how the service is automatically started.

**Hint:**
Examine systemd services and configuration files to find persistence mechanisms.

**Validation:**
The system should validate that the student has identified the systemd service unit file responsible for the suspicious service's persistence.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement. Look for any file transfers, remote command execution, or other indicators that the attacker might be moving to other systems within the network.

**Hint:**
Check for any scheduled tasks, cron jobs, or other mechanisms that might facilitate lateral movement.

**Validation:**
The system should validate that the student has identified the payload-transfer service and its associated timer, which are used for lateral movement.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating and responding to the Earth Lusca malware family, specifically the KTLVdoor backdoor, while adhering to the Incident Response security profile. The scenario uses only the hosts, services, and artifacts present in the sandbox, and it does not invent any indicators or infrastructure details.