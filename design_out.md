### INFO_LEVEL
**Scenario Title:** Sednit Xagent Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Sednit Xagent backdoor infection on a compromised network. The Sednit group is known for using Xagent for long-term monitoring and espionage. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify suspicious services and processes.
- Investigate persistence mechanisms.
- Analyze network communication for command-and-control (C2) activity.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual activity on the target host. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:**
Check the running services and look for any that seem out of place or unfamiliar.
**Validation:**
The service name is splm.dll.service.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. Investigate the persistence mechanisms used by the service.
**Hint:**
Look for systemd services or cron jobs that might be responsible for starting the service automatically.
**Validation:**
The persistence mechanism is the systemd service splm.dll.service.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication.
**Hint:**
Check the network connections and listen ports associated with the suspicious service.
**Validation:**
The C2 port number is 4444.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.