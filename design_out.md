### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. Your goal is to identify and analyze the malicious activity, contain the threat, and ensure the system is secure.

**Learning Objectives:**
- Identify and investigate suspicious services.
- Determine network ports used for suspicious communication.
- Analyze logs and network traffic for evidence of data exfiltration.
- Identify and remove persistence mechanisms.
- Collect forensic evidence supporting the identified malicious activity.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
Identify and investigate an unauthorized or suspicious service running on the target host that communicates with an external server.
**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services. Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.
**Hint:**
Check the running services and look for any that seem out of place or have unusual descriptions.
**Validation:**
The service name "systemkernelservicedefender.service" should be identified.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
Determine which network port is used for the suspicious communication identified in the previous task.
**Learning Objective:**
Inspect the C2 service definitions and pay particular attention to ExecStart, which specifies the command launched by the service with a port number as an argument.
**Hint:**
Examine the service configuration for the suspicious service to find the port number.
**Validation:**
The port number "80" should be identified.

### TRAINING_LEVEL 3
**Task:** Evidence Collection
**Description:**
Collect forensic evidence supporting the identified malicious activity, including logs, process information, service configuration, and network evidence.
**Learning Objective:**
Gather relevant logs, process information, service configuration, and network evidence to support the investigation.
**Hint:**
Look for logs and configuration files related to the suspicious service and any network connections it makes.
**Validation:**
The script "/usr/local/bin/local-inventory.sh" should be identified and collected as evidence.