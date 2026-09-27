### INFO_LEVEL
**Scenario Title:** Tsunami/Kaiten Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux server that has been infected with the Tsunami/Kaiten backdoor. This malware is known for its IRC/Bot capabilities, including flooder and backdoor functionalities. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms used by the malware.
- Analyze network communications for command and control (C2) activity.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the server, you noticed unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:**
Look for systemd services, cron jobs, or other scheduled tasks that might be responsible for starting the suspicious service.
**Validation:**
The hidden flag is the name of the persistence mechanism or the service responsible for it.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command and control (C2) server. Identify the network port used for this communication to better understand the threat.
**Hint:**
Use network monitoring tools to inspect active connections and identify the port used by the suspicious service.
**Validation:**
The hidden flag is the port number used for C2 communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and focuses on realistic investigation and mitigation steps.