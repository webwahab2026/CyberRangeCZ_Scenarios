### INFO_LEVEL
**Scenario Title:** Investigation of Sofacy Malware Activity  
**Scenario Description:** In this exercise, participants will investigate a suspected Sofacy malware infection on a target host. The malware is known to be a backdoor that can install itself with or without root privileges. Participants will analyze the system for signs of compromise, focusing on service discovery, persistence mechanisms, and suspicious files.  
**Learning Objectives:**  
- Understand the behavior of Sofacy malware and its implications for system security.  
- Develop skills in identifying and investigating suspicious services and files.  
- Gain experience in collecting evidence and analyzing system logs.

### ACCESS_LEVEL
**Entry Host:** target  
**Username:** cyrano  
**Password:** cyrano  
**Access Method:** SSH  
**Privilege Boundaries:** Participants will have sudo privileges on the target host. They will not have direct access to the c2-server or next-target without lateral movement.  

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery  
**Description:** You have been alerted to potential malicious activity on the target host. Your first task is to identify any unauthorized or suspicious services running on the system. Use the appropriate commands to enumerate the running services and determine if any of them are unusual.  
**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.  
**Hidden Flag:** Service name of the suspicious service.  
**Hint:** Check for services that are not typically installed on a standard Ubuntu system.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery  
**Description:** After identifying a suspicious service, your next step is to determine how this service is configured to start automatically after a reboot. Investigate the system for any persistence mechanisms that may be in place.  
**Learning Objective:** Identify persistence mechanisms (e.g., systemd services, cron jobs).  
**Hidden Flag:** Service name or persistence identifier.  
**Hint:** Look for systemd service files in `/etc/systemd/system/` or check for any scheduled tasks.

### TRAINING_LEVEL 3
**Task:** Suspicious File Discovery  
**Description:** You suspect that the suspicious service is associated with a malicious file. Your task is to locate the executable or file related to the suspicious activity. Investigate the file system and correlate processes with files on disk to identify any malicious artifacts.  
**Learning Objective:** Correlate processes with files on disk and identify malicious artifacts.  
**Hidden Flag:** Filename or file path of the malicious artifact.  
**Hint:** Review the contents of `/home/cyrano/` and check for any unusual files that may have been created recently.