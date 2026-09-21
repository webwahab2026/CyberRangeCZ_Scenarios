### INFO_LEVEL
**Scenario Title:** Rakos Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious SSH brute force attempts originating from an internal server. Initial analysis suggests the presence of the Rakos Linux backdoor malware, which is known to create botnets by compromising devices with weak passwords. Your task is to investigate and respond to this incident.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network traffic for signs of command-and-control (C2) communication.
- Investigate lateral movement and data exfiltration attempts.
- Contain and eradicate the malware.

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
Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
Now that you have identified the suspicious service, determine which network port it is using for communication. This information is crucial for understanding the malware's command-and-control (C2) infrastructure.
**Hint:**
Use network monitoring tools to inspect the ports being used by the suspicious service.
**Validation:**
The C2 port number must be identified and reported.

### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:**
The Rakos malware is known to perform lateral movement by brute-forcing SSH logins. Investigate the target host to find evidence of lateral movement attempts to other hosts in the network.
**Hint:**
Check the SSH logs and system logs for any unauthorized access attempts or connections to other hosts.
**Validation:**
The destination host and any evidence of lateral movement must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is feasible within the sandbox environment and adheres to the strict constraints outlined.