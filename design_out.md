Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** VoIP Platform Incident Response

**Scenario Description:**
You are an incident responder tasked with investigating and responding to a security incident involving a compromised VoIP platform. The platform is running on Linux servers and has been targeted by the CDRThief malware, which exfiltrates call detail records (CDR) from the compromised softswitch. Your mission is to investigate the incident, identify the malicious activity, and contain the threat.

**Scenario Learning Objectives:**
1. Investigate suspicious services and processes on Linux systems
2. Analyze network traffic for signs of command-and-control (C2) communication
3. Identify and contain lateral movement within the network
4. Gather forensic evidence to support incident response activities

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

**Additional Hosts:**
- next-target (IP: 192.168.50.6)
- c2-server (IP: 192.168.40.5)

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring the target VoIP platform, you noticed unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.

**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Hint:** Use standard Linux commands to list running services and check their status.

**Q/A:**
Q: What is the name of the suspicious service running on the target host?
A: callservice

---

**TRAINING_LEVEL 2**
**Task Title:** C2 Communication Discovery (Port)

**Task Description:**
Now that you've identified the suspicious service, investigate its network activity. Determine which network port is used for the suspicious communication.

**Learning Objective:** Investigate network traffic and identify suspicious ports.

**Hint:** Use network monitoring tools to inspect the service's network connections.

**Q/A:**
Q: Which network port is used for the suspicious communication?
A: 80

---

**TRAINING_LEVEL 3**
**Task Title:** Lateral Movement Investigation

**Task Title:** Lateral Movement Investigation

**Task Description:**
Analyze the target host for signs of lateral movement. Identify any file transfers or remote execution used to move between hosts within the network.

**Learning Objective:** Correlate events across hosts to identify attacker lateral movement.

**Hint:** Check for any scheduled tasks, cron jobs, or systemd timers that might facilitate lateral movement.

**Q/A:**
Q: What is the name of the service responsible for lateral movement?
A: payload-transfer

---

**Scenario Validation:**
1. Verify that the suspicious service (callservice) is identified and investigated.
2. Confirm that the C2 communication port (80) is discovered.
3. Ensure that the lateral movement service (payload-transfer) is identified and analyzed.

**Scenario Completion:**
Upon successful completion of all tasks, you will have gathered sufficient evidence to understand the extent of the compromise and taken initial steps to contain the threat. Further investigation and remediation may be required to fully eradicate the malware and restore the integrity of the VoIP platform.

---

This scenario is strictly aligned with the provided sandbox environment, MISP event, and security profile. All tasks are designed to be feasible within the given topology and Ansible configuration, and they adhere to the training level examples provided. The scenario focuses on investigating and responding to the CDRThief malware, which targets VoIP platforms and exfiltrates call detail records.