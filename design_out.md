### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based system. The Fysbis malware is known for exfiltrating sensitive documents and spying on user activities. Your goal is to identify and analyze the malicious activity, contain the threat, and remove the malware from the infected systems.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network traffic for signs of command-and-control (C2) communication.
- Detect and mitigate lateral movement within the network.
- Collect forensic evidence and verify the removal of the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target system, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.
**Hint:**
Check the list of running services and look for any that are not part of the standard system configuration.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
Now that you have identified the suspicious service, determine which network port it is using for communication. This will help you understand how the malware is connecting to its command-and-control server.
**Learning Objective:**
Investigate network traffic and identify suspicious ports.
**Hint:**
Use network monitoring tools to observe the ports being used by the suspicious service.
**Validation:**
The hidden flag is the C2 port number.

### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:**
Examine the target host for evidence of lateral movement. Identify any file transfers or remote execution activities that indicate the attacker is moving between hosts within the network.
**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.
**Hint:**
Check logs and system configurations for any unusual file transfers or remote execution commands.
**Validation:**
The hidden flag is the service name or script used for lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.