### INFO_LEVEL
**Scenario Title:** Sandworm Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sandworm intrusion set, specifically targeting Centreon systems with the Exaramel backdoor. Your goal is to identify and mitigate the threat posed by this backdoor, which provides remote access and control capabilities to the attackers.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms used by the backdoor.
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
While monitoring the target system, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services that might be responsible for this activity.
**Hint:** Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
- The student must identify the suspicious service running on the target host.
- Expected Answer: bkd.service

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the backdoor.
**Hint:** Investigate systemd services and timers to find how the service is scheduled to run.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- Expected Answer: systemd timer

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication to better understand the threat.
**Hint:** Analyze network connections and listen ports to identify the port used by the suspicious service.
**Validation:**
- The student must identify the network port used for C2 communication.
- Expected Answer: 4444

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.