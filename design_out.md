Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in your organization's high-performance computing (HPC) environment. Kobalos is a sophisticated backdoor malware that targets HPC clusters and other high-profile systems. It provides remote access, terminal session capabilities, and credential stealing functionality.

Your mission is to investigate the compromised systems, identify the malware's persistence mechanisms, and contain the threat.

**Scenario Objectives:**
1. Identify and investigate suspicious services and processes
2. Determine the malware's persistence mechanisms
3. Investigate lateral movement and data exfiltration
4. Contain the threat and remove malicious artifacts

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring your organization's HPC environment, you noticed unusual network traffic originating from the target host. Your first task is to identify any unauthorized or suspicious services running on this host that might be responsible for this activity.

**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Task Validation:**
The hidden flag is the name of the suspicious service.

**Hint:** Use standard Linux commands to list running services and check their legitimacy.

---

**TRAINING_LEVEL 2**
**Task Title:** Persistence Discovery

**Task Description:**
Now that you've identified a suspicious service, you need to determine how it maintains persistence on the system. Investigate the system's startup mechanisms to find out how the service is automatically started after reboot.

**Learning Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Task Validation:**
The hidden flag is the name of the service or its persistence identifier.

**Hint:** Check systemd services and timers, as well as cron jobs.

---

**TRAINING_LEVEL 3**
**Task Title:** Lateral Movement Investigation

**Task Title:** Lateral Movement Investigation

**Task Description:**
Your investigation has revealed that the malware might be attempting to move laterally within your network. Examine the system for evidence of file transfers or remote execution used to move between hosts. Focus on any connections to the next-target host (IP: 192.168.50.6).

**Learning Objective:** Correlate events across hosts to identify attacker lateral movement.

**Task Validation:**
The hidden flag is the name of the service, filename, or destination host involved in lateral movement.

**Hint:** Investigate systemd services, timers, and any scripts or binaries related to file transfers.

---

This scenario is designed to be deployed in the KYPO/CyberRangeCZ platform and strictly aligns with the provided sandbox environment, MISP event, and security profile. The tasks are structured to guide students through the investigation of a Kobalos malware infection, focusing on service discovery, persistence mechanisms, and lateral movement. The scenario adheres to the sandbox alignment rules and MISP constraints, ensuring that all tasks are feasible within the given environment and use only the provided indicators.