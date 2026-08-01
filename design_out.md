### INFO_LEVEL
**Scenario Title:** Tsunami/Kaiten Incident Response

**Scenario Description:**
You are an incident responder tasked with investigating and responding to a Tsunami/Kaiten.c backdoor infection on a Linux server. This malware functions as an IRC bot with flooder and backdoor capabilities, exploiting web admin panel abuse to gain root access via crontab UID. Your goal is to identify, contain, and eradicate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms and remove them.
- Analyze network traffic for command-and-control (C2) communication.
- Collect forensic evidence and verify containment.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target server, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.
**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Learning Objective:**
Identify persistence mechanisms such as systemd, cron, or scheduled tasks.
**Hint:**
Look for systemd services, cron jobs, or other scheduled tasks that might be responsible for starting the suspicious service.
**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Investigate the network traffic associated with the suspicious service to determine which port is used for command-and-control (C2) communication. This information is crucial for containing the threat.
**Learning Objective:**
Analyze network traffic and identify suspicious ports used for C2 communication.
**Hint:**
Use network monitoring tools to inspect open ports and active connections related to the suspicious service.
**Validation:**
The hidden flag is the port number used for C2 communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.