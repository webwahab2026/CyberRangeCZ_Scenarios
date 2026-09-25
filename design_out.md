### INFO_LEVEL
**Scenario Title:** Sandworm Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sandworm malware family, specifically the Exaramel backdoor. This backdoor is known to ensure persistence via a scheduled task (Cron) and communicates with its command and control (C2) servers via HTTPS. Your mission is to identify, investigate, and mitigate the threat.

**Learning Objectives:**
- Identify and investigate unauthorized or suspicious services running on a host.
- Determine how the suspicious service is automatically started after reboot.
- Locate the executable or file associated with the suspicious activity.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound HTTPS traffic from the target host. Investigate the target host to identify any unauthorized or suspicious services running that could be responsible for this traffic.
**Hint:** Check the running services and look for any that seem out of place or unfamiliar.
**Validation:**
- The student must identify the suspicious service running on the target host.
- Expected Answer: bkd.service

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:** Investigate systemd services and timers to find how the service is scheduled to run.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- Expected Answer: lab-checkin.timer

### TRAINING_LEVEL 3
**Task:** Suspicious File Discovery
**Description:**
Locate the executable or file associated with the suspicious service you identified earlier. This will help you gather more information about the malware and its behavior.
**Hint:** Check the service configuration files and look for the executable path.
**Validation:**
- The student must identify the file associated with the suspicious service.
- Expected Answer: /usr/local/bin/lab-checkin.sh