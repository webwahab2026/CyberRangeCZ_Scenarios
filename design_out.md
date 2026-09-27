Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Linux/Rakos Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on its Linux servers. Initial analysis suggests a possible compromise by the Linux/Rakos backdoor malware. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target server with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring the target server, you've noticed unusual outbound connections to a high port number. Investigate these connections to determine if they're malicious.
**Hint:** Check the network connections and listening ports on the target server.
**Validation:** The task is considered successful if the student identifies the suspicious port number used for C2 communication.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Process
**Description:** You've identified a suspicious process running on the target server. Analyze this process to determine its purpose and origin.
**Hint:** Look for unusual processes and examine their command lines, paths, and parent processes.
**Validation:** The task is considered successful if the student identifies the suspicious process name and its associated file.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** You suspect that the attacker might be attempting to move laterally within the network. Investigate the target server for any signs of lateral movement.
**Hint:** Check for any unusual file transfers or remote command executions.
**Validation:** The task is considered successful if the student identifies the service or mechanism used for lateral movement.

---

This scenario is aligned with the provided MISP event, security profile, and sandbox environment. It focuses on investigating the Linux/Rakos backdoor malware, which spreads via brute force SSH logins and creates a web server for C2 communication. The tasks are designed to test the student's ability to identify suspicious network connections, analyze processes, and investigate lateral movement, all of which are relevant to the Incident Response security profile.

The scenario uses only the hosts, services, and file paths that exist in the sandbox environment, and it relies on the indicators present in the MISP event. The tasks are structured to guide the student through the investigation process while maintaining the integrity of the sandbox environment.