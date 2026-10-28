### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis malware is known to be a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of ELF binaries and can install itself with or without root privileges.

Your goal is to identify and investigate the suspicious activity, determine the extent of the compromise, and take appropriate containment measures.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the running services and look for any that seem out of place or unfamiliar.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
You have identified a suspicious service running on the target host. Determine how this service is automatically started after a system reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd services and timers to find any related to the suspicious service.

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to identify any unusual activity.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and focuses on realistic investigation and containment measures.