# Xbash Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Xbash ransomware. This malware combines ransomware, coinmining, and worm-like self-propagation capabilities. It targets Linux-based systems for ransomware and botnet capabilities and Microsoft Windows-based systems for coinmining and self-propagation. The ransomware component targets and deletes Linux-based databases. It spreads by attacking weak passwords and unpatched vulnerabilities.

Your task is to investigate the incident, identify the indicators of compromise, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server?

**Hint:** Check the network connections and logs on the victim host.

**Answer:** 192.168.90.5

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Question:** What is the port number used for the command-and-control communication?

**Hint:** Investigate the network traffic and logs on the victim host.

**Answer:** 4443

## TRAINING_LEVEL 3
**Task:** Identify a file or a dataset that was transferred outside the environment before encryption.

**Question:** What is the name of a file that was exfiltrated from the victim host?

**Hint:** Analyze the logs and file access records on the victim host.

**Answer:** quarterly_report.txt

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and containment of the Xbash ransomware incident, focusing on discovering indicators through system and network analysis.