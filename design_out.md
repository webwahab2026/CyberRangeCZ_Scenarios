### INFO_LEVEL
**Scenario Title:** SLOWPULSE Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected compromise involving the SLOWPULSE backdoor malware on a Pulse Secure VPN appliance. The malware is known to maintain persistence, facilitate lateral movement, and exfiltrate data. Your mission is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms.
- Analyze network traffic for command-and-control (C2) communication.
- Collect forensic evidence and contain the threat.

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
**Task:** Persistence Discovery
**Description:**
Now that you have identified a suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:**
Investigate systemd services and timers to find any related to the suspicious service.
**Validation:**
The persistence mechanism (service name or persistence identifier) must be identified and reported.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication to help contain the threat.
**Hint:**
Analyze network connections and listen ports to identify the suspicious port.
**Validation:**
The C2 port number must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.