# Linux P2P Ransom Botnet Investigation

## INFO_LEVEL
The victim host in your network has been compromised by a Linux P2P Ransom botnet. This malware combines ransomware capabilities with botnet functionality, targeting Linux systems. It uses a peer-to-peer (P2P) network for communication and command and control (C2) purposes, making it resilient to traditional takedown methods.

Your task is to investigate the compromised system, identify the indicators of compromise, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

The victim host IP address is 192.168.90.10.

## TRAINING_LEVEL 1
**Task:** Determine the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server?

**Hint:** Investigate network connections and logs to identify suspicious outbound communication.

## TRAINING_LEVEL 2
**Task:** Identify a file or dataset that was transferred outside the environment before encryption.

**Question:** What is the name of a file that was exfiltrated from the victim host?

**Hint:** Examine logs and network activity to determine what data was exfiltrated.

## TRAINING_LEVEL 3
**Task:** Locate the ransom note left on the compromised system.

**Question:** What is the path to the ransom note?

**Hint:** Investigate filesystem artifacts generated following encryption.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Linux P2P Ransom botnet, identifying indicators of compromise, and containing the threat. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and artifacts present in the MISP event and the sandbox environment.