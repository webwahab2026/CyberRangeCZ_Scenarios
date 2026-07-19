### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious network activity originating from one of its Linux servers. Initial analysis suggests the presence of a sophisticated backdoor known as BRICKSTORM. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network connections for command-and-control communications.
- Contain and eradicate the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:**
Check the list of running services and look for any that appear unusual or unauthorized.
**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (IP)
**Description:**
Now that you have identified the suspicious service, determine the remote IP address it is communicating with. This will help you understand the command-and-control infrastructure.
**Hint:**
Analyze the network connections associated with the suspicious service to find the remote IP address.
**Validation:**
The hidden flag is the C2 IP address.

### TRAINING_LEVEL 3
**Task:** Process Termination
**Description:**
To prevent further damage, you need to stop the malicious process associated with the suspicious service. Terminate the process while minimizing impact on legitimate services.
**Hint:**
Identify the process responsible for the suspicious activity and use appropriate commands to terminate it.
**Validation:**
The hidden flag is the process name or service name.