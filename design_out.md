Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Sofacy Fysbis Investigation**

**INFO_LEVEL:**
The target network has been compromised by the Sofacy group using their Fysbis malware. Your task is to investigate the compromise, identify the malicious activity, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the system and access other hosts as needed.

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Activity
**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host. Investigate this activity to identify the source of the connections.
**Hint:** Check the systemd services and look for any unusual or unfamiliar services.
**Validation:**
The task is considered successful if the student identifies the `systemkernelservicedefender.service` service as suspicious.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:**
You've identified a suspicious service. Now, analyze it to understand its behavior and determine if it's related to the Fysbis malware.
**Hint:** Examine the service unit file and the script it executes.
**Validation:**
The task is considered successful if the student identifies that the service connects to port 80 on the c2-server host with the message "systemkernelservicedefender".

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
Check if the attacker has attempted to move laterally from the target host to other hosts in the network.
**Hint:** Look for any scripts or services that transfer files or execute commands on remote hosts.
**Validation:**
The task is considered successful if the student identifies the `payload-transfer.sh` script and the `payload-transfer.service` that transfers files to the next-target host.

---

This scenario is aligned with the provided MISP event, security profile, and sandbox environment. It focuses on investigating the Fysbis malware, identifying its behavior, and containing the threat. The tasks are designed to be feasible within the given sandbox and require students to actively investigate and analyze the system.