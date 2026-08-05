### INFO_LEVEL
**Scenario Title:** UPSTYLE Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious activity on one of its Linux servers. Initial analysis suggests the presence of a backdoor named UPSTYLE. Your task is to investigate, analyze, and respond to this cybersecurity incident.

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
While monitoring the server, you noticed an unusual service running. Investigate the running services on the target host and identify any suspicious or unauthorized services.
**Hint:** Check the systemd services and look for any services that seem out of place.
**Validation:**
- The student must identify the suspicious service running on the target host.
- Expected output: update.py.service

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Determine how the suspicious service is automatically started after a reboot. Identify the persistence mechanism used by the service.
**Hint:** Examine the systemd unit files and timers.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- Expected output: update.py.timer

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Investigate the network traffic to determine which port is used for the suspicious communication. Identify the port used by the suspicious service to communicate with an external command-and-control server.
**Hint:** Check the network connections and listen ports.
**Validation:**
- The student must identify the port used for the suspicious communication.
- Expected output: 443