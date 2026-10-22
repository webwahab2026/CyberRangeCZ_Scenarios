### INFO_LEVEL
**Scenario Title:** XOR.DDoS Incident Response

**Scenario Description:**
You are an incident responder tasked with investigating and responding to an XOR.DDoS malware infection on a Linux-based host. The malware is designed to force infected hosts to participate in large DDoS attack campaigns. Your goal is to identify the malicious activity, contain the threat, and remove the malware from the infected host.

**Scenario Objectives:**
1. Identify the malicious service running on the infected host.
2. Determine how the malicious service persists on the host.
3. Locate and remove the malicious executable and associated artifacts.
4. Block communication between the compromised host and the external command-and-control server.
5. Verify that the threat has been successfully removed.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the host.

**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Your task is to identify and investigate any unauthorized or suspicious services running on the host that could be responsible for this activity.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of running services and look for any that are not part of the standard system configuration.

**Validation:**
The hidden flag is the name of the suspicious service.

### TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Description:**
You have identified a suspicious service running on the host. Your next task is to determine how this service is automatically started after a system reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Check the systemd service files and timers to see if the suspicious service is configured to start automatically.

**Validation:**
The hidden flag is the name of the systemd service or persistence identifier.

### TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Description:**
You have identified the suspicious service and its persistence mechanism. Your next task is to locate the executable or file associated with this suspicious activity.

**Learning Objective:**
Correlate processes with files on disk and identify malicious artifacts.

**Hint:**
Check the process information and look for the executable path associated with the suspicious service.

**Validation:**
The hidden flag is the filename or file path of the malicious executable.