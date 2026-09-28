Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Xbash Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity potentially related to the Xbash malware family. As an incident responder, your task is to investigate and contain this threat. Xbash is known to combine botnet, ransomware, and coinmining capabilities, targeting both Linux and Windows systems. It can delete databases, create ransom messages, and demand Bitcoin payments for data recovery.

**ACCESS_LEVEL:**
You have SSH access to the target host (192.168.50.5) with the following credentials:
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:** While monitoring the target host, you've noticed unusual network activity. Investigate the host to identify any unauthorized or suspicious services running.
**Hint:** Check running services and their associated processes.
**Validation:** The service name should be identified.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
**Description:** Now that you've identified a suspicious service, determine which network port it's using for communication. This information is crucial for containing the threat.
**Hint:** Investigate network connections and open ports associated with the suspicious service.
**Validation:** The C2 port number should be identified.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:** Evidence suggests that the attacker might be attempting to move laterally within the network. Investigate the target host to find any signs of file transfers or remote execution to other hosts.
**Hint:** Check for any scheduled tasks, cron jobs, or other mechanisms that might facilitate lateral movement.
**Validation:** The service name, filename, or destination host should be identified.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. It focuses on the Incident Response security profile and uses only the indicators and hosts present in the topology and Ansible data. The tasks are designed to guide students through the investigation and containment process while maintaining the integrity of the sandbox environment.