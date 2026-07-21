### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious network activity originating from an internal host. Initial analysis suggests the presence of a backdoor malware named BRICKSTORM. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network connections for command-and-control communications.
- Contain the threat by blocking malicious communications and removing persistence mechanisms.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the host `target`. Investigate the running services on this host to identify any unauthorized or suspicious services.
**Hint:**
Check the list of running services and look for any that appear unusual or unauthorized.
**Question:**
What is the name of the suspicious service running on the host `target`?
**Answer:**
updatemgr.service

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (IP)
**Description:**
The suspicious service identified in the previous task is likely communicating with a command-and-control (C2) server. Determine the remote IP address that the service is contacting.
**Hint:**
Use network monitoring tools to inspect active connections and identify the destination IP address.
**Question:**
What is the IP address of the command-and-control server that the suspicious service is communicating with?
**Answer:**
192.168.40.5

### TRAINING_LEVEL 3
**Task:** Process Termination
**Description:**
To prevent further malicious activity, you need to stop the suspicious process associated with the backdoor. Identify and terminate the process while minimizing impact on legitimate services.
**Hint:**
Use process management tools to identify and terminate the malicious process.
**Question:**
What is the name of the process that you terminated to stop the malicious activity?
**Answer:**
lab-checkin.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and uses only the services, hosts, and artifacts that exist within the defined infrastructure. The tasks are structured to guide students through the investigation and containment of the BRICKSTORM backdoor while adhering to the constraints and requirements specified.