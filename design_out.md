### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection on a high-performance computing (HPC) cluster. Kobalos is a complex malware that targets HPC clusters and other high-profile systems, providing remote access, terminal sessions, and credential stealing capabilities. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify suspicious services and processes.
- Investigate lateral movement and data exfiltration.
- Contain and eradicate the malware.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:** Check the list of running services and look for any that seem out of place.
**Validation:**
- The student must identify the suspicious service running on port 7070.
- Expected output: OpenSSHserver

### TRAINING_LEVEL 2
**Task:** Lateral Movement Investigation
**Description:**
You suspect that the malware might be moving laterally within the network. Investigate the target host to find evidence of file transfers or remote execution used to move between hosts.
**Hint:** Check the system logs and network connections for any unusual activity.
**Validation:**
- The student must identify the service responsible for lateral movement.
- Expected output: payload-transfer.service

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Determine which network port is used for the suspicious communication between the target host and the external command-and-control server.
**Hint:** Analyze the network traffic and identify the port used for the suspicious communication.
**Validation:**
- The student must identify the port used for C2 communication.
- Expected output: 7070