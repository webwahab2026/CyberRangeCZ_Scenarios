Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: BlackTech PLEAD Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the BlackTech threat group. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring network traffic, you've noticed unusual outbound connections from the target host. Investigate these connections to determine if they're malicious.
**Hint:** Check active network connections and listen ports on the target host.
**Validation:** The task is considered successful if the student identifies the suspicious port (4444) used for command and control communication.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:** You've discovered a suspicious service running on the target host. Analyze this service to understand its behavior and determine if it's related to the BlackTech threat group.
**Hint:** Examine the service configuration and logs to understand its purpose and behavior.
**Validation:** The task is considered successful if the student identifies the service name (bkd.service) and its associated configuration files.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** Evidence suggests that the attacker may have moved laterally from the target host to another system. Investigate this possibility and determine if sensitive data has been exfiltrated.
**Hint:** Check for file transfers and remote execution commands involving other hosts in the network.
**Validation:** The task is considered successful if the student identifies the service (payload-transfer.service) responsible for lateral movement and the destination host (next-target).

---

This scenario aligns with the provided MISP event, security profile, and sandbox environment. It focuses on investigating the PLEAD backdoor malware, which is known for establishing persistent connections to command and control (C2) servers, executing commands, and exfiltrating data. The tasks require students to identify suspicious network connections, analyze a malicious service, and investigate lateral movement, all of which are key aspects of incident response as defined by the NICE framework.

The scenario uses only the hosts, services, and file paths that exist in the sandbox environment, as described in the topology and Ansible configuration. The tasks are designed to be technically feasible and require students to investigate and analyze the provided artifacts to uncover the hidden flags.