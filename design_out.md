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
Examine the systemd service files and timers to understand how the service is maintained.

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
- For TRAINING_LEVEL 1: Service name
- For TRAINING_LEVEL 2: Service name or persistence identifier
- For TRAINING_LEVEL 3: C2 port number

**Validation:**
The answers provided by the student will be checked against the expected service names, persistence identifiers, and C2 port numbers derived from the sandbox environment.