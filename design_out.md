### INFO_LEVEL
**Scenario Title:** Exaramel Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Exaramel backdoor malware on a Linux-based system. Your goal is to identify, analyze, and contain the threat to prevent further damage.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms used by malware.
- Analyze network communications for command-and-control (C2) activity.
- Collect forensic evidence and contain the threat.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the system, you noticed unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:** Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
- The student must identify the suspicious service running on the target host.
- Expected output: The service name "bkd.service".

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:** Investigate systemd services and timers to find how the service is scheduled to run.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- Expected output: The service name or persistence identifier "lab-checkin.timer".

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication to help contain the threat.
**Hint:** Analyze network connections and listen ports to identify the suspicious port.
**Validation:**
- The student must identify the network port used for the suspicious communication.
- Expected output: The C2 port number "4444".

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise for incident responders.