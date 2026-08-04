Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** Fancy Bear C2 Investigation

**INFO_LEVEL:**
- The target network has been compromised by the Fancy Bear malware family.
- Your task is to investigate and respond to this incident.
- The malware is known to use blogspot domains for command and control (C2) purposes.
- The malware exhibits lateral movement capabilities and exfiltrates data.

**ACCESS_LEVEL:**
- Entry host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Network Connections
**Description:**
While monitoring the target host, you notice unusual outbound network connections. Investigate these connections to identify any suspicious activity.
**Hint:** Check the network connections and look for unusual destinations or ports.
**Validation:**
- The student should identify the connection to the C2 server (192.168.40.5) on port 4444.
- The student should recognize that this connection is suspicious due to the unusual destination and port.

**TRAINING_LEVEL 2:**
**Task:** Analyze Suspicious Service
**Description:**
You've identified a suspicious network connection. Now, investigate the service responsible for this connection. Determine how it's started and what files are associated with it.
**Hint:** Look for services that might be responsible for the suspicious network connection.
**Validation:**
- The student should identify the service named "bkd.service".
- The student should find that the service is started using systemd.
- The student should locate the executable file associated with the service.

**TRAINING_LEVEL 3:**
**Task:** Investigate Lateral Movement
**Description:**
The malware is known to exhibit lateral movement capabilities. Investigate if the malware has moved laterally to other hosts in the network.
**Hint:** Check for any file transfers or remote execution between hosts.
**Validation:**
- The student should identify the service named "payload-transfer.service" on the target host.
- The student should find that this service transfers files to the next-target host (192.168.50.6).
- The student should recognize that this is evidence of lateral movement.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. It focuses on investigating the Fancy Bear malware, identifying its C2 communications, analyzing its persistence mechanisms, and investigating its lateral movement capabilities. The tasks are designed to be feasible within the given sandbox and require the student to actively investigate and analyze the environment.