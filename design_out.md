Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Linux/Rakos Backdoor Investigation**

**INFO_LEVEL:**
The network has detected unusual outbound connections from the target host (192.168.50.5). Your task is to investigate and contain this potential Linux/Rakos backdoor infection.

**ACCESS_LEVEL:**
- Entry host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Connections
**Description:** The target host is making unusual outbound connections. Identify the suspicious network activity and determine which port is being used for this communication.
**Hint:** Check the system logs and network connections to find the suspicious port.
**Validation:** The correct port number (between 20000-60000) must be identified.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:** A suspicious service is running on the identified port. Investigate this service to understand its behavior and persistence mechanism.
**Hint:** Examine the systemd services and running processes to find the suspicious service.
**Validation:** The service name must be correctly identified.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:** The malware may be attempting to spread to other hosts. Investigate any evidence of lateral movement from the target host to next-target (192.168.50.6).
**Hint:** Check for any scheduled tasks or scripts that transfer files to other hosts.
**Validation:** The script or service responsible for lateral movement must be identified.

---

This scenario aligns with the provided MISP event for the Linux/Rakos backdoor, the Incident Response security profile, and the sandbox environment defined by the topology and Ansible configuration. The tasks are designed to guide students through investigating the malware's network activity, service behavior, and lateral movement capabilities, all within the constraints of the available sandbox resources.