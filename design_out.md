Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Sofacy Fysbis Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Sofacy group's Fysbis Linux backdoor. Your task is to investigate and respond to this potential compromise.

**ACCESS_LEVEL:**
You have SSH access to the target host (192.168.50.5) with the username "cyrano" and password "cyrano". From this host, you can access the next-target host (192.168.50.6) using SSH.

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host to port 80. Investigate this activity and determine if it's related to the Sofacy Fysbis backdoor.

**Hint:**
Check running services and systemd timers that might be responsible for this network activity.

**Validation:**
The hidden flag is the name of the suspicious service responsible for the outbound connections.

**TRAINING_LEVEL 2:**
**Task:** Analyze Persistence Mechanism
**Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate the persistence mechanism and document your findings.

**Hint:**
Look for systemd service files and timers that might be responsible for starting the suspicious service.

**Validation:**
The hidden flag is the name of the systemd service or timer responsible for the persistence.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Examine the target host for evidence of lateral movement to other systems in the network. Identify any file transfers or remote execution attempts that might indicate the attacker is moving laterally.

**Hint:**
Check for rsync processes, SSH connections, and file transfer logs that might indicate lateral movement.

**Validation:**
The hidden flag is the name of the service, filename, or destination host that indicates lateral movement.

---

This scenario is aligned with the provided MISP event, security profile, and sandbox environment. It focuses on investigating the Sofacy Fysbis backdoor, which is a modular Linux backdoor with C2 capabilities and persistence mechanisms. The tasks are designed to test the student's ability to investigate suspicious network activity, analyze persistence mechanisms, and identify lateral movement, all of which are relevant to the Incident Response security profile.

The scenario uses only the hosts, services, and file paths that exist in the sandbox environment, as described in the topology and Ansible configuration. The tasks are based on the observable indicators and behaviors described in the MISP event, and they do not reveal any hidden implementation details. The validation flags are based on the actual services, files, and hosts in the sandbox, ensuring that the scenario is strictly aligned with the provided environment.