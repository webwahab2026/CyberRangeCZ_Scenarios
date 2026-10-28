### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in a high-performance computing (HPC) environment. Kobalos is a complex, multiplatform malware that targets HPC clusters and other high-profile systems. It grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms used by malware.
- Analyze network traffic for command-and-control (C2) communication.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.
**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified a suspicious service, determine how it is automatically started after a system reboot. Investigate the persistence mechanisms used by the malware.
**Learning Objective:**
Identify persistence mechanisms such as systemd, cron, or scheduled tasks.
**Hint:**
Look for systemd services, cron jobs, or other scheduled tasks that might be responsible for starting the suspicious service.
**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this communication.
**Learning Objective:**
Investigate network traffic and identify suspicious ports.
**Hint:**
Use network monitoring tools to identify open ports and active connections.
**Validation:**
The hidden flag is the C2 port number.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and relies on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The tasks are structured to guide students through the investigation process while maintaining the integrity of the sandbox environment.