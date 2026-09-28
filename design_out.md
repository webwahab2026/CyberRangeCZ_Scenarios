Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Earth Lusca Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Earth Lusca malware family, specifically the KTLVdoor backdoor. Your team has been tasked with investigating and responding to this potential security incident.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:** While monitoring network traffic, you've noticed unusual outbound connections from the target host. Investigate the host to identify any unauthorized or suspicious services that might be responsible for this activity.
**Hint:** Check running services and their associated processes.
**Validation:** The service name should be identified.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
**Description:** Now that you've identified a suspicious service, determine which network port it's using for communication. This information is crucial for containing the threat.
**Hint:** Examine the service configuration and network connections.
**Validation:** The C2 port number should be identified.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:** You suspect that the attacker might be attempting to move laterally within the network. Investigate the target host for any evidence of file transfers or remote execution to other hosts.
**Hint:** Check for any scheduled tasks or services that might be transferring files to other hosts.
**Validation:** The service name, filename, or destination host should be identified.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating and responding to the Earth Lusca malware family, specifically the KTLVdoor backdoor, while adhering to the Incident Response security profile. The tasks are designed to be feasible within the given topology and Ansible configuration, and they follow the guidelines provided in the training level examples.