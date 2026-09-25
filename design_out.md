# Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by ransomware. Your task is to investigate the incident, identify the threat, and contain the damage. The victim host is running a Linux operating system and has been exhibiting unusual behavior.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server?

**Hint:** Check network connections and logs for suspicious outbound connections.

**Validation:** The answer should be the IP address of the c2-server.

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Question:** What is the port number used for the command-and-control communication?

**Hint:** Investigate network traffic to identify unusual ports.

**Validation:** The answer should be the port number used by the ransomware for command-and-control communication.

## TRAINING_LEVEL 3
**Task:** Identify a file or a dataset that was transferred outside the environment before encryption.

**Question:** What is the name of a file that was exfiltrated from the victim host?

**Hint:** Analyze logs and network activity to determine what data was exfiltrated.

**Validation:** The answer should be the name of a file that was exfiltrated to the exfil-server.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a ransomware incident, focusing on identifying the command-and-control server, the exfiltrated data, and the ransom note. The scenario encourages students to use their incident response skills to analyze network connections, investigate logs, and identify suspicious activity.