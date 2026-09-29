### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis malware is known for its modular capabilities, including command-and-control (C2) communication, exfiltration, and persistence mechanisms. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms and lateral movement techniques.
- Collect and analyze forensic evidence to understand the scope of the compromise.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the `target` host. Investigate the host to identify any unauthorized or suspicious services running on the system.
**Hint:** Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
- The student must identify the suspicious service running on the `target` host.
- The hidden flag is the service name.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the attacker.
**Hint:** Investigate systemd services and timers to find any related to the suspicious service.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- The hidden flag is the service name or persistence identifier.

### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:**
Examine the `target` host for evidence of lateral movement. Identify any file transfers or remote execution techniques used to move between hosts within the network.
**Hint:** Check system logs and network connections for any unusual activity involving the `next-target` host.
**Validation:**
- The student must identify the service or script responsible for lateral movement.
- The hidden flag is the service name or script.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.