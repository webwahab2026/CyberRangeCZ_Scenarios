Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis Linux backdoor. The malware is known to establish command and control (C2) communication and exfiltrate data. Your mission is to identify and contain this threat within the network.

**Scenario Objectives:**
1. Identify suspicious services and processes
2. Investigate C2 communication
3. Contain the threat

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
While monitoring the target system, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.

**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Hint:** Use standard Linux commands to list running services and check their status.

**Validation:**
- Expected Answer: bkd.service
- Validation Method: Command
- Validation Command: systemctl status bkd.service

---

**TRAINING_LEVEL 2**
**Task Title:** C2 Communication Discovery (Port)

**Task Description:**
Now that you've identified a suspicious service, investigate its network activity. Determine which network port is used for the suspicious communication.

**Learning Objective:** Investigate network traffic and identify suspicious ports.

**Hint:** Check the service configuration and network connections.

**Validation:**
- Expected Answer: 80
- Validation Method: Command
- Validation Command: ss -tulnp | grep bkd.service

---

**TRAINING_LEVEL 3**
**Task Title:** C2 Containment

**Task Description:**
Based on your findings, implement containment measures to block communication between the compromised host and the external command-and-control server.

**Learning Objective:** Apply network controls or firewall rules to contain the threat.

**Hint:** Use the firewall to block the identified port.

**Validation:**
- Expected Answer: iptables -A INPUT -p tcp --dport 80 -j DROP
- Validation Method: Command
- Validation Command: iptables -L -n | grep DROP

---

**Scenario Completion:**
Congratulations! You have successfully identified and contained the Sofacy Fysbis backdoor on the target system. Your actions have prevented further C2 communication and potential data exfiltration.

**Debrief:**
1. Review the steps you took to identify the suspicious service.
2. Analyze the network traffic to understand the C2 communication.
3. Discuss the containment measures you implemented and their effectiveness.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on the Sofacy Fysbis backdoor and its known behavior, using only indicators explicitly present in the MISP event. The tasks follow the training level examples in style and complexity while maintaining alignment with the sandbox reality.