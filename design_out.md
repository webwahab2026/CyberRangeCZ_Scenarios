### INFO_LEVEL
**Scenario Title:** PACHA Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious activity on several Linux servers. Initial analysis suggests the presence of the PACHA backdoor malware, known for its coinmining capabilities, persistence mechanisms, and lateral movement. Your task is to investigate, analyze, and respond to this cybersecurity incident.

**Learning Objectives:**
- Identify and investigate unauthorized or suspicious services.
- Determine persistence mechanisms used by the malware.
- Analyze network traffic for command-and-control (C2) communication.
- Investigate lateral movement techniques.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the host to identify any unauthorized or suspicious services running on it.
**Hint:**
Check running services and their associated processes.
**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:**
Investigate systemd services, cron jobs, or other scheduled tasks.
**Validation:**
The persistence mechanism (e.g., systemd service name) must be identified and reported.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Analyze the network traffic to determine which port is used for the suspicious communication between the target host and the potential command-and-control server.
**Hint:**
Use network monitoring tools to inspect outgoing connections.
**Validation:**
The C2 port number must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.