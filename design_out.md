Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential BRICKSTORM backdoor infection on your organization's Linux systems. The backdoor uses sophisticated techniques including SOCKS proxying, multi-layered web service communication, and varied command execution to obscure its activities. Your mission is to identify, contain, and eradicate this threat.

**Scenario Learning Objectives:**
1. Identify and investigate suspicious services and processes
2. Analyze network communications for command-and-control activity
3. Investigate lateral movement techniques
4. Contain and eradicate the threat

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Scenario Duration:** 2 hours

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Access:**
From the entry host, you can SSH to next-target (IP: 192.168.50.6) using the same credentials.

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring system logs on the target host, you noticed unusual network activity. Investigate the running services on this host to identify any unauthorized or suspicious services.

**Task Instructions:**
1. Connect to the target host using the provided credentials
2. Enumerate all running services and processes
3. Identify any services or processes that appear suspicious or unauthorized
4. Document your findings, including the service name, process ID, and any relevant details

**Validation:**
The system will check if you've identified the suspicious service with the correct name.

**Hint:**
Look for services that don't match the expected software inventory for this system. Pay attention to unusual process names, high network usage, or services listening on unexpected ports.

---

**TRAINING_LEVEL 2**
**Task Title:** C2 Communication Discovery

**Task Description:**
You've identified a suspicious service on the target host. Now investigate its network communications to determine if it's connecting to a command-and-control server.

**Task Instructions:**
1. Analyze the network connections associated with the suspicious service
2. Identify any external IP addresses or domains it's communicating with
3. Determine the network ports being used for this communication
4. Document your findings, including the destination IP, port, and any patterns in the communication

**Validation:**
The system will check if you've correctly identified the C2 communication details.

**Hint:**
Use network monitoring tools to capture and analyze the traffic. Look for unusual connection patterns, such as regular check-ins or data exfiltration.

---

**TRAINING_LEVEL 3**
**Task Title:** Lateral Movement Investigation

**Task Description:**
You suspect the BRICKSTORM backdoor might be attempting to move laterally within your network. Investigate the target host for any signs of lateral movement to other systems.

**Task Instructions:**
1. Examine the target host for any evidence of file transfers or remote command execution
2. Check for any established connections to other hosts in the network
3. Investigate system logs for any unauthorized access attempts or data transfers
4. Document your findings, including the destination host, transferred files, and any relevant details

**Validation:**
The system will check if you've correctly identified the lateral movement activity.

**Hint:**
Look for SSH connections, file transfer utilities, or remote command execution tools. Check system logs for any unusual access patterns or data transfers.

---

**Scenario Completion:**
Once you've completed all tasks and contained the threat, submit your findings through the KYPO/CyberRangeCZ interface. Your report should include details of the suspicious service, C2 communication, lateral movement, and the actions you took to contain and eradicate the threat.

**Scenario Debrief:**
After completing the scenario, you'll receive a debriefing that includes:
1. The correct answers to each task
2. An explanation of the BRICKSTORM backdoor's behavior
3. Recommendations for preventing similar incidents in the future

---

This scenario is designed to be deployed in the KYPO/CyberRangeCZ platform and strictly aligns with the provided sandbox environment, MISP event, and security profile. The tasks are structured to guide students through the incident response process while maintaining the integrity of the sandbox and using only the available indicators and artifacts.