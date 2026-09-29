Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: XOR.DDoS Incident Response**

**INFO_LEVEL:**
The organization has detected unusual network activity on its Linux servers. Initial analysis suggests a possible XOR.DDoS malware infection, specifically the Groundhog variant. Your team is responsible for investigating, analyzing, and responding to this potential cybersecurity incident.

**ACCESS_LEVEL:**
You have SSH access to the target server with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:** While monitoring the target server, you've noticed unusual network activity. Investigate the running services on the target server to identify any unauthorized or suspicious services.
**Hint:** Check the systemd services and look for any unusual or unexpected services.
**Validation:** The service name (bkd.service) must be identified.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
**Description:** Now that you've identified a suspicious service, investigate its network activity. Determine which network port is used for the suspicious communication.
**Hint:** Use network monitoring tools to identify open ports and their associated processes.
**Validation:** The C2 port number (4444) must be identified.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:** Investigate the target server for any signs of lateral movement. Identify any file transfers or remote execution used to move between hosts.
**Hint:** Check the system logs and look for any unusual file transfers or remote command executions.
**Validation:** The service name (payload-transfer.service) must be identified.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks are designed to guide students through the investigation and response process for the XOR.DDoS malware infection, specifically the Groundhog variant. The scenario focuses on the Incident Response security profile and uses only the indicators and artifacts present in the MISP event and sandbox environment.