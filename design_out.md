# Linux P2P Ransom Botnet Incident Response Scenario

## INFO_LEVEL
The victim host in your network has been compromised by the Linux P2P Ransom botnet ransomware. This malware combines ransomware capabilities with botnet functionality, spreading through peer-to-peer networks and encrypting files on infected systems. The malware also has command-and-control (C2) capabilities, allowing it to receive instructions from remote servers and participate in botnet activities.

Your task is to investigate the incident, identify the indicators of compromise, and take appropriate containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the command-and-control server IP address communicating with the compromised system.

**Hint:** Check network connections and process activity logs to find suspicious outbound connections.

**Validation:** The correct C2 server IP address is 192.168.90.5.

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Hint:** Investigate network traffic and process activity to identify the port used by the ransomware for C2 communication.

**Validation:** The correct C2 port number is 4443.

## TRAINING_LEVEL 3
**Task:** Locate the ransom note left on the compromised system.

**Hint:** Search the victim's home directory for files that indicate ransomware activity.

**Validation:** The correct ransom note filename is /home/cyrano/RANSOM_NOTE.txt.