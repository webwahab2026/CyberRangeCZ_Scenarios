# Linux P2P Ransom Botnet Investigation

## INFO_LEVEL
The victim host in your network has been compromised by the Linux P2P Ransom botnet ransomware. This malware combines ransomware capabilities with botnet functionality, spreading through peer-to-peer networks and encrypting files on infected systems. It also has command-and-control (C2) capabilities, allowing it to receive instructions from remote servers and participate in botnet activities.

Your task is to investigate the compromised system, identify the indicators of compromise, and take appropriate containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify the command-and-control server IP address used by the ransomware.

**Hint:** Check network connections and process communications on the victim host.

**Question:** What is the IP address of the command-and-control server?

## TRAINING_LEVEL 2
**Task:** Determine which network port is used for suspicious command-and-control communication.

**Hint:** Investigate network traffic and process communications on the victim host.

**Question:** What is the port number used for command-and-control communication?

## TRAINING_LEVEL 3
**Task:** Identify the external host receiving sensitive data from the compromised system.

**Hint:** Analyze outbound network traffic and SSH connections on the victim host.

**Question:** What is the IP address of the exfiltration server?