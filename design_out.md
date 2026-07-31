### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis malware is known to be a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of ELF binaries and can install itself with or without root privileges.

Your goal is to identify and investigate the suspicious activity, determine the extent of the compromise, and take appropriate containment measures.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
You have identified a suspicious service running on the target host. Determine how this service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to understand how the suspicious service is maintained.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
Investigate the network traffic associated with the suspicious service to determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Use network monitoring tools to capture and analyze the traffic from the suspicious service.

### Validation
**Expected Answer Format:**
- **TRAINING_LEVEL 1:** The name of the suspicious service.
- **TRAINING_LEVEL 2:** The persistence mechanism used by the suspicious service.
- **TRAINING_LEVEL 3:** The network port used for the suspicious communication.

### Scoring
- **TRAINING_LEVEL 1:** 30 points
- **TRAINING_LEVEL 2:** 30 points
- **TRAINING_LEVEL 3:** 40 points

### Complexity
**Difficulty Level:** Intermediate

### Flags
- **TRAINING_LEVEL 1:** systemkernelservicedefender.service
- **TRAINING_LEVEL 2:** systemd timer
- **TRAINING_LEVEL 3:** 80

### Additional Notes
- Ensure that all tasks are aligned with the provided sandbox environment and MISP event.
- Do not invent any hosts, services, or indicators that are not explicitly present in the provided data.
- Use only the indicators and behaviors described in the MISP event for threat intelligence elements.