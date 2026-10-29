### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis malware is a modular Linux backdoor that can install itself with or without root privileges. Your goal is to identify and analyze the suspicious activity, contain the threat, and remove the malware from the affected systems.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network traffic for signs of command-and-control (C2) communication.
- Contain and eradicate the malware to prevent further compromise.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the `target` host. Investigate the host to identify any unauthorized or suspicious services running on the system.
**Hint:**
Check the list of running services and look for any that appear unusual or unauthorized.
**Validation:**
The service name is `bkd`.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
Now that you have identified the suspicious service, determine which network port it is using for communication. This information is crucial for containing the threat.
**Hint:**
Investigate the network connections associated with the suspicious service.
**Validation:**
The C2 port number is `80`.

### TRAINING_LEVEL 3
**Task:** Process Termination
**Description:**
To prevent further communication with the command-and-control server, you need to stop the malicious process. Identify and terminate the process associated with the suspicious service.
**Hint:**
Use process management commands to identify and terminate the malicious process.
**Validation:**
The process name is `ncat`.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and artifacts within the sandbox environment, ensuring a realistic and deployable exercise.