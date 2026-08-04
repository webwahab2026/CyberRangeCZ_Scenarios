### INFO_LEVEL
**Scenario Title:** CrossRAT Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential CrossRAT infection on a target system. CrossRAT is a backdoor malware capable of remote access and control, data exfiltration, and maintaining persistence on infected systems. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify suspicious services and processes.
- Investigate persistence mechanisms.
- Analyze network communication for command-and-control (C2) activity.
- Collect forensic evidence.
- Contain and eradicate the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target system, you notice unusual network activity. Investigate the running services on the target system to identify any unauthorized or suspicious services.
**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified a suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:**
Investigate systemd services and timers to find any related to the suspicious service.
**Validation:**
The persistence mechanism (service name or persistence identifier) must be identified and reported.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Analyze the network traffic associated with the suspicious service to determine which port is used for command-and-control (C2) communication. This information is crucial for containing the threat.
**Hint:**
Use network monitoring tools to inspect the traffic and identify the suspicious port.
**Validation:**
The C2 port number must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is feasible within the sandbox environment and adheres to the strict constraints outlined.