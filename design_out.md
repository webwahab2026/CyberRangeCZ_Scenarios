# Xbash Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Xbash ransomware. This malware combines ransomware, coinmining, and self-propagation capabilities, targeting both Linux and Windows systems. Your task is to investigate the incident, identify the indicators of compromise, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server that the ransomware is communicating with?

**Hint:** Investigate network connections and logs to find suspicious outbound connections.

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Question:** What network port is the ransomware using to communicate with the command-and-control server?

**Hint:** Examine network traffic and service logs to identify unusual port usage.

## TRAINING_LEVEL 3
**Task:** Identify files or datasets that were transferred outside the environment before encryption.

**Question:** What files were exfiltrated from the victim host to an external server?

**Hint:** Analyze logs and network traffic to determine what data was sent out of the network.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through investigating the Xbash ransomware incident, focusing on discovering indicators of compromise through system and network analysis.