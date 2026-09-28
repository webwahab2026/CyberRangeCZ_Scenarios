Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** Fancy Bear Incident Response

**Scenario Description:**
A sophisticated cyber espionage group known as Fancy Bear has been detected in your network. Your task is to investigate, analyze, and respond to this incident following the Incident Response profile.

**INFO_LEVEL:**
- The Fancy Bear group is known for its sophisticated cyber espionage activities.
- They use backdoors for persistent access to compromised systems.
- The group is capable of lateral movement, exfiltration, and maintaining persistence.
- The malware family targets Windows, Linux, and macOS platforms.

**ACCESS_LEVEL:**
- Entry host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Suspicious Service Discovery
**Description:**
While monitoring your network, you noticed unusual outbound connections from the target host. Investigate the host to identify any unauthorized or suspicious services running.
**Hint:** Check running services and their associated processes.
**Validation:**
- The student should identify the suspicious service running on port 4444.
- Expected answer: bkd.service

**TRAINING_LEVEL 2:**
**Task:** Persistence Discovery
**Description:**
Now that you've identified the suspicious service, determine how it is automatically started after reboot. This will help you understand the attacker's persistence mechanism.
**Hint:** Investigate systemd services and timers.
**Validation:**
- The student should identify the systemd timer responsible for starting the suspicious service.
- Expected answer: lab-checkin.timer

**TRAINING_LEVEL 3:**
**Task:** Lateral Movement Investigation
**Description:**
Investigate if the attacker has moved laterally from the target host to other hosts in the network. Look for evidence of file transfers or remote execution.
**Hint:** Check for any services or processes responsible for transferring data between hosts.
**Validation:**
- The student should identify the service responsible for transferring data from target to next-target.
- Expected answer: payload-transfer.service

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. It focuses on the Incident Response profile and uses only the indicators and hosts present in the topology and Ansible data. The tasks are designed to be feasible within the given sandbox and follow the training level examples provided.