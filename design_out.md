Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario Name:** Kobalos Malware Investigation

**Objective:** Investigate and respond to a Kobalos malware infection in a high-performance computing environment.

**Entry Point:**
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

---

**INFO_LEVEL:**
1. You are a cybersecurity analyst responding to an alert about suspicious activity on the target host.
2. The target host is part of a high-performance computing cluster running Ubuntu.
3. Initial analysis suggests the presence of the Kobalos malware, a complex backdoor that targets HPC clusters.
4. Your goal is to investigate the infection, identify the scope, and contain the threat.

---

**ACCESS_LEVEL:**
1. SSH access to the target host (192.168.50.5) as user cyrano with password cyrano.
2. From the target host, you can SSH to next-target (192.168.50.6) as user cyrano without a password.
3. The c2-server (192.168.40.5) is not directly accessible from the target host.

---

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service running on the target host.
**Description:**
1. Investigate running services on the target host.
2. Identify any suspicious or unexpected services.
3. The service name is the flag.
**Hint:** Check systemd services and look for any services related to payload transfer or check-in.
**Q/A:**
- Q: What is the name of the suspicious service?
- A: payload-transfer.service

---

**TRAINING_LEVEL 2:**
**Task:** Investigate the suspicious outbound connection.
**Description:**
1. Analyze network connections from the target host.
2. Identify any suspicious outbound connections.
3. The destination port is the flag.
**Hint:** Check the systemd timer and service files for the suspicious service.
**Q/A:**
- Q: What is the destination port of the suspicious outbound connection?
- A: 7070

---

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication.
**Description:**
1. Based on your previous findings, contain the C2 communication.
2. The port number used to contain the communication is the flag.
**Hint:** Use firewall rules to block the identified port.
**Q/A:**
- Q: What is the port number you used to contain the C2 communication?
- A: 7070

---

**Validation:**
1. The scenario will be validated by checking the completion of all tasks and the correctness of the flags.
2. The flags should be submitted in the order of the tasks (TRAINING_LEVEL 1, TRAINING_LEVEL 2, TRAINING_LEVEL 3).

---

**Debriefing:**
1. After completing the scenario, a debriefing will be provided.
2. The debriefing will include the correct steps to investigate and contain the Kobalos malware.
3. It will also provide additional resources for further learning and practice.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event, focusing on the investigation and containment of the Kobalos malware. The tasks are designed to be realistic and challenging, reflecting the complexity of the malware and the environment.