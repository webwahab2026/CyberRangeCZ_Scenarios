# Ransomware Incident Response Scenario

## INFO_LEVEL
This scenario presents a ransomware incident affecting a Linux system. Your task is to investigate the compromise, identify indicators of compromise, and contain the threat.

The victim system has shown signs of unusual activity, including encrypted files and network connections to unknown hosts. Your mission is to analyze the situation, determine the scope of the compromise, and implement containment measures.

## ACCESS_LEVEL
You have SSH access to the victim system with the following credentials:
- Host: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Determine the external host communicating with the compromised system.

**Objective:** Analyze network connections and identify the ransomware command-and-control server.

**Hint:** Check the system logs for any unusual outbound connections.

**Validation:** The correct C2 IP address must be identified.

## TRAINING_LEVEL 2
**Task:** Identify a file or a dataset that was transferred outside the environment before encryption.

**Objective:** Analyze logs, file access records, and network activity to determine what data was exfiltrated.

**Hint:** Investigate the network traffic and file transfer logs.

**Validation:** The correct exfiltrated filename must be identified.

## TRAINING_LEVEL 3
**Task:** Locate the ransom note left on the compromised system.

**Objective:** Investigate filesystem artifacts generated following encryption.

**Hint:** Search for files with unusual names or content in the user's home directory.

**Validation:** The correct ransom note filename must be identified.