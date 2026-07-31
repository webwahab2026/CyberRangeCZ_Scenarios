### INFO_LEVEL
**Scenario Title:** Sednit Xagent Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Sednit Xagent backdoor infection on a compromised network. The Sednit group is known for using Xagent for espionage activities, including executing commands from a remote server, collecting sensitive information, and maintaining persistence on infected systems. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms used by the malware.
- Analyze network traffic for command-and-control (C2) communications.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual activity on the target host. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.
**Hint:**
Check the systemd services and look for any services that seem out of place.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified a suspicious service, determine how it is automatically started after a system reboot. Investigate the persistence mechanisms used by the service.
**Learning Objective:**
Identify persistence mechanisms such as systemd, cron, or scheduled tasks.
**Hint:**
Examine the systemd service files and timers.
**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication.
**Learning Objective:**
Investigate network traffic and identify suspicious ports.
**Hint:**
Check the network connections and listen ports.
**Validation:**
The hidden flag is the C2 port number.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and relies on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The tasks are structured to guide students through the investigation process while maintaining the integrity of the sandbox environment.