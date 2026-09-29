Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis Linux backdoor. The backdoor is known to be a modular trojan with C2 capabilities. Your mission is to identify, analyze, and contain this threat within our test environment.

**Scenario Objectives:**
1. Identify suspicious services and processes
2. Investigate persistence mechanisms
3. Analyze C2 communication patterns
4. Contain and eradicate the threat

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

**Additional Access:**
From target, you can SSH to next-target (IP: 192.168.50.6) using the same credentials.

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring system logs on target, you noticed unusual network activity. Investigate the running services on this host to identify any suspicious or unauthorized services.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Validation:**
The system should validate that the student identifies the suspicious service name.

**Hint:**
Check running services and look for anything unusual or unexpected.

---

**TRAINING_LEVEL 2**
**Task Title:** Persistence Discovery

**Task Description:**
Now that you've identified a suspicious service, determine how it maintains persistence on the system. Investigate how this service is automatically started after system reboots.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Validation:**
The system should validate that the student identifies the persistence mechanism used by the suspicious service.

**Hint:**
Check systemd services and timers for anything related to the suspicious service.

---

**TRAINING_LEVEL 3**
**Task Title:** C2 Communication Discovery (Port)

**Task Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Validation:**
The system should validate that the student identifies the correct C2 port number.

**Hint:**
Monitor network connections associated with the suspicious service.

---

**Scenario Completion:**
Once you've completed all tasks and contained the threat, submit your findings for review.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and artifacts from the topology and Ansible configuration. The scenario focuses on investigating the Sofacy Fysbis backdoor while adhering to the security profile of an Incident Responder.