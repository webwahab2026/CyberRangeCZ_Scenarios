Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: BRICKSTORM Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on its internal systems. Your team has been tasked with investigating a potential BRICKSTORM backdoor infection. This sophisticated malware uses SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. It combines several techniques including DoH, nested TLS encryption, and the abuse of legitimate cloud services to evade detection.

**ACCESS_LEVEL:**
You have access to the target system (192.168.50.5) as user 'cyrano' with password 'cyrano'. From this system, you can investigate potential lateral movement to next-target (192.168.50.6) using SSH.

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:** While monitoring the target system, you've noticed unusual network connections. Investigate the running services on the target system to identify any unauthorized or suspicious services.
**Hint:** Check the systemd services and look for any that might be related to network communication.
**Validation:** The service name 'vnetd.service' should be identified as suspicious.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
**Description:** Now that you've identified a suspicious service, determine which network port it's using for communication. This information is crucial for understanding the attack vector and planning containment measures.
**Hint:** Use network monitoring tools to observe active connections from the suspicious service.
**Validation:** The port number '443' should be identified as the C2 communication port.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:** Examine the target system for evidence of lateral movement. The attacker might be using this system to pivot to other systems within the network.
**Hint:** Investigate scheduled tasks, cron jobs, and any scripts that might be transferring files or executing commands on other systems.
**Validation:** The service name 'payload-transfer.service' and the destination host 'next-target' should be identified as part of the lateral movement.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating the BRICKSTORM backdoor while adhering to the security profile of an Incident Response team. The tasks are designed to be feasible within the given sandbox and require students to discover information through investigation rather than being explicitly told what to look for.