### INFO_LEVEL
**Scenario Title:** UPSTYLE Backdoor Investigation

**Scenario Description:**
Your organization has detected suspicious activity on one of its Linux servers. Initial analysis suggests the presence of a backdoor named UPSTYLE. Your task is to investigate, analyze, and respond to this cybersecurity incident.

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
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.
**Question:**
What is the name of the suspicious service running on the target host?
**Answer:**
bkd.service

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. This will help you understand the persistence mechanism used by the attacker.
**Hint:**
Investigate the systemd services and timers to find how the suspicious service is started.
**Question:**
What is the name of the systemd timer responsible for starting the suspicious service?
**Answer:**
lab-checkin.timer

### TRAINING_LEVEL 3
**Task:** Suspicious File Discovery
**Description:**
Locate the executable or file associated with the suspicious service. This will help you gather more information about the backdoor and its behavior.
**Hint:**
Check the service unit file to find the path to the executable.
**Question:**
What is the path to the executable associated with the suspicious service?
**Answer:**
/usr/local/bin/lab-checkin.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and relies on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The tasks are structured to guide students through the investigation process without revealing hidden implementation details.