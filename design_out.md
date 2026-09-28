Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: UPSTYLE Backdoor Investigation**

**INFO_LEVEL:**
The organization has detected unusual network activity on its internal systems. Your team has been tasked with investigating a potential compromise involving a backdoor malware named UPSTYLE. This malware is known to execute additional commands via specially crafted network requests and has been observed on Linux systems.

**ACCESS_LEVEL:**
You have access to the target system as user 'cyrano' with password 'cyrano'. The target system is connected to other systems in the network that may have been affected.

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target system, you noticed an unusual service running. Investigate the running services on the target system and identify any suspicious or unauthorized services.
**Hint:** Check the systemd services and look for any services that don't belong to standard system applications.
**Validation:**
The service name is stored in /tmp/flag1.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this suspicious communication.
**Hint:** Investigate the network connections made by the suspicious service.
**Validation:**
The C2 port number is stored in /tmp/flag2.

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:**
There is evidence that the attacker may have moved laterally from the target system to another system in the network. Investigate file transfers or remote execution used to move between hosts.
**Hint:** Check the system logs and network connections for any signs of lateral movement.
**Validation:**
The destination host is stored in /tmp/flag3.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. The tasks focus on investigating the UPSTYLE backdoor malware, identifying its communication methods, and determining if the attacker has moved laterally within the network. The scenario follows the NICE Incident Response profile and uses only the indicators and artifacts present in the MISP event and sandbox environment.