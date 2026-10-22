Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Sednit Xagent Investigation**

**INFO_LEVEL:**
The Sednit group, also known as APT29, is a sophisticated cyber espionage group believed to be operating out of Russia. They are known for targeting government agencies, diplomatic institutions, and research organizations. Their primary malware, Xagent, is a backdoor used for espionage purposes.

In this scenario, you will investigate a compromised network where the Sednit group's Xagent malware has been detected. Your goal is to identify the malware's presence, understand its behavior, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:** While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the host to identify any unauthorized or suspicious services running.
**Hint:** Check the running services and their associated processes.
**Validation:** The service name is lg3.exe.service.

**TRAINING_LEVEL 2:**
**Task:** Persistence Discovery
**Description:** Now that you've identified the suspicious service, determine how it is automatically started after reboot. This will help you understand the malware's persistence mechanism.
**Hint:** Investigate systemd services and timers.
**Validation:** The persistence identifier is lab-checkin.timer.

**TRAINING_LEVEL 3:**
**Task:** C2 Communication Discovery (Port)
**Description:** The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this communication.
**Hint:** Investigate the service configuration and network connections.
**Validation:** The C2 port number is 4444.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. It focuses on the Sednit group's Xagent malware and follows the NICE Incident Response profile. The tasks are designed to guide students through the investigation process while maintaining the integrity of the sandbox environment.