### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in a high-performance computing (HPC) environment. Kobalos is a complex malware that targets HPC clusters and other high-profile systems, providing remote access, credential stealing, and lateral movement capabilities. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Enumerate running services and distinguish legitimate from suspicious services.
- Identify persistence mechanisms associated with suspicious services.
- Correlate processes with files on disk and identify malicious artifacts.
- Analyze logs and network traffic to identify exfiltration and lateral movement.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services that might be communicating with an external command-and-control (C2) server.
**Hint:**
Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior may also indicate suspicious activity.
**Validation:**
The service name `lab-checkin.timer` should be identified as suspicious.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
Now that you have identified a suspicious service, determine which network port is used for the suspicious communication. This information is crucial for understanding the attack vector and planning mitigation strategies.
**Hint:**
Inspect the service's configuration file to find the port number specified in the ExecStart command.
**Validation:**
The C2 port number `7070` should be identified.

### TRAINING_LEVEL 3
**Task:** Persistence Discovery
**Description:**
Determine how the suspicious service is automatically started after reboot. Identifying the persistence mechanism is essential for removing the malware and preventing reinfection.
**Hint:**
Look for timers or other persistence mechanisms associated with the suspicious service.
**Validation:**
The timer name `lab-checkin.timer` should be identified as the persistence mechanism.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and mitigation of a Kobalos malware infection, focusing on service discovery, communication analysis, and persistence identification.