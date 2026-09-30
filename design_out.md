### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis malware is known for its remote shell access, persistence mechanisms, and command and control (C2) communication capabilities. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms.
- Analyze network communication for signs of C2 activity.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services running.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.

**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified a suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the attacker.

**Learning Objective:**
Identify persistence mechanisms such as systemd, cron, or scheduled tasks.

**Hint:**
Examine systemd services and timers to find any related to the suspicious service.

**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Investigate the network traffic to determine which port is being used for the suspicious communication between the target host and the potential command-and-control server.

**Learning Objective:**
Analyze network traffic and identify suspicious ports used for C2 communication.

**Hint:**
Check the network connections and listen ports to find any unusual or unexpected ports.

**Validation:**
The hidden flag is the port number used for the suspicious communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.