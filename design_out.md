# Xbash Ransomware Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Xbash ransomware. This malware combines ransomware, coinmining, and self-propagation capabilities, targeting both Linux and Windows systems. Your task is to investigate the incident, identify the indicators of compromise, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the command-and-control server IP address used by the ransomware.

**Hint:** Check network connections and logs for suspicious outbound connections.

**Question:** What is the IP address of the command-and-control server?

**Answer:** 192.168.90.5

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious data exfiltration.

**Hint:** Investigate network traffic to identify ports associated with exfiltration activity.

**Question:** What is the network port used for data exfiltration?

**Answer:** 22

## TRAINING_LEVEL 3
**Task:** Locate the ransom note left on the compromised system.

**Hint:** Search the victim's home directory for files with suspicious content.

**Question:** What is the full path to the ransom note?

**Answer:** /home/cyrano/RANSOM_NOTE.txt