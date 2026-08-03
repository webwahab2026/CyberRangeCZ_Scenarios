### INFO_LEVEL
**Scenario Title:** Pulse Secure VPN Compromise Investigation

**Scenario Description:**
Your organization has detected unusual activity on its Pulse Secure VPN appliances. Initial analysis suggests a potential compromise by the RADIALPULSE backdoor malware. Your task is to investigate the compromised hosts, identify the malware's behavior, and contain the threat.

**Learning Objectives:**
- Investigate compromised hosts for signs of malware.
- Identify and analyze suspicious services and processes.
- Contain the threat by blocking malicious communication and removing persistence mechanisms.

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
You have identified a suspicious service running on the target host. Determine how this service is automatically started after a system reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine systemd services and timers to find any related to the suspicious service.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to find the one used by the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.