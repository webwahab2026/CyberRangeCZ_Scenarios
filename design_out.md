Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sandworm Intrusion Set Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sandworm intrusion set. The P.A.S. webshell has been detected in your environment, which is known to be used for remote access and control. Your mission is to investigate the compromised systems, identify the malicious activity, and contain the threat.

**Scenario Learning Objectives:**
1. Identify and investigate suspicious services and processes
2. Analyze network communications for command-and-control activity
3. Investigate lateral movement techniques
4. Contain and remediate the identified threats

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

**TRAINING_LEVEL 1**
**Task:** Suspicious Service Discovery

**Task Description:**
While monitoring your network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services that might be responsible for this activity.

**Hint:** Check running services and their associated processes.

**Validation:**
The task is considered successful if the student identifies the suspicious service named "bkd.service".

---

**TRAINING_LEVEL 2**
**Task:** C2 Communication Discovery (Port)

**Task Description:**
Now that you've identified a suspicious service, investigate its network activity. Determine which network port is being used for the suspicious communication.

**Hint:** Examine the service configuration and network connections.

**Validation:**
The task is considered successful if the student identifies the C2 port number 4444.

---

**TRAINING_LEVEL 3**
**Task:** Lateral Movement Investigation

**Task Description:**
Investigate if the compromised host is being used to move laterally within your network. Identify any file transfers or remote execution techniques used to move between hosts.

**Hint:** Check for scheduled tasks, cron jobs, or other persistence mechanisms that might facilitate lateral movement.

**Validation:**
The task is considered successful if the student identifies the "payload-transfer.service" responsible for lateral movement.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating the Sandworm intrusion set and the P.A.S. webshell, as described in the MISP event. The tasks are designed to challenge the student's incident response skills, as outlined in the security profile.