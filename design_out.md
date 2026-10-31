# Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by ransomware. Your task is to investigate the incident, identify the threat, and contain the damage. The victim host is running a Linux operating system and has been exhibiting unusual network activity. Your goal is to understand the scope of the compromise, identify the command and control infrastructure, and prevent further data exfiltration.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the external host communicating with the compromised system.

**Objective:** Analyze network connections and identify the ransomware command-and-control server.

**Hint:** Check the network connections and logs on the victim host to find suspicious outbound connections.

**Validation:** The correct C2 IP address must be identified.

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Objective:** Investigate network traffic to identify ports used by the ransomware.

**Hint:** Examine the network logs and active connections to find the port used for C2 communication.

**Validation:** The correct C2 port number must be identified.

## TRAINING_LEVEL 3
**Task:** Identify the external host receiving sensitive data from the compromised system.

**Objective:** Analyze outbound network traffic to identify the exfiltration infrastructure.

**Hint:** Look for unusual data transfers and network connections that indicate exfiltration activity.

**Validation:** The correct exfiltration IP address must be identified.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a ransomware incident, focusing on identifying command and control communication and data exfiltration. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.