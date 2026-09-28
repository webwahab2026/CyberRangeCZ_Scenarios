### INFO_LEVEL
**Scenario Title:** Sandworm Exaramel Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sandworm Exaramel backdoor malware. This malware is known for its persistence, C2 communication, and lateral movement capabilities. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Determine persistence mechanisms.
- Analyze network communication for signs of C2 activity.
- Investigate lateral movement techniques.
- Collect and verify evidence of malicious activity.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:** Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation:**
- The student must identify the suspicious service running on port 4444.
- Expected output: "bkd.service"

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. Investigate the persistence mechanisms used by the service.
**Hint:** Look for systemd service files or cron jobs that might be responsible for starting the service.
**Validation:**
- The student must identify the systemd service unit file responsible for the persistence of the suspicious service.
- Expected output: "/etc/systemd/system/bkd.service"

### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:**
Exaramel malware is known for its lateral movement capabilities. Investigate the target host to identify any evidence of file transfers or remote execution used to move between hosts.
**Hint:** Check the system logs and network connections for any unusual activity involving the next-target host.
**Validation:**
- The student must identify the service responsible for the lateral movement activity.
- Expected output: "payload-transfer.service"