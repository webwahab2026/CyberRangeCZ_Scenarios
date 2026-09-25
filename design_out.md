### INFO_LEVEL
**Scenario Title:** CrossRAT Incident Response

**Scenario Description:**
You are an incident responder tasked with investigating and responding to a CrossRAT malware infection. CrossRAT is a backdoor tool capable of targeting Windows, OSX, and Linux systems, allowing attackers to exfiltrate data and maintain persistence. Your goal is to identify the infection, understand its behavior, and contain the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms.
- Analyze network traffic for command-and-control (C2) communication.
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
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services running.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
You have identified a suspicious service. Determine how this service is automatically started after a system reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Investigate systemd services and timers to find how the suspicious service is maintained.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Analyze the network traffic to determine which port is used for the suspicious communication between the target host and the potential command-and-control server.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to find the one used by the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.