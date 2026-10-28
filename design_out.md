# Xbash Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Xbash ransomware. This malware combines ransomware, coinmining, and self-propagation capabilities, targeting both Linux and Windows systems. It spreads by attacking weak passwords and unpatched vulnerabilities. The malware is data-destructive, deleting Linux-based databases as part of its ransomware capabilities.

Your task is to investigate the incident, identify the indicators of compromise, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

You can use this access to investigate the system and gather evidence.

## TRAINING_LEVEL 1
**Task:** Identify the command-and-control server IP address used by the ransomware.

**Hint:** Check the network connections and logs on the victim host to find any suspicious outbound connections.

**Question:** What is the IP address of the command-and-control server?

## TRAINING_LEVEL 2
**Task:** Determine the network port used for suspicious command-and-control communication.

**Hint:** Investigate the network traffic and logs to identify the port associated with the ransomware's command-and-control communication.

**Question:** What is the port number used for the command-and-control communication?

## TRAINING_LEVEL 3
**Task:** Identify a file or dataset that was transferred outside the environment before encryption.

**Hint:** Analyze the logs, file access records, and network activity to determine what data was exfiltrated.

**Question:** What is the name of a file or dataset that was exfiltrated?

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to encourage investigation and discovery of the indicators of compromise within the sandbox environment.