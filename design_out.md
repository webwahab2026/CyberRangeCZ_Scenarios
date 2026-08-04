# Tsunami/Kaiten Incident Response Scenario

## INFO_LEVEL
The target system has exhibited unusual network activity, including unauthorized connections to external IRC servers and suspicious file transfers. Your task is to investigate and respond to this potential security incident involving the Tsunami/Kaiten malware.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious network connections on the target system.

**Objective:** Identify and document any unauthorized or suspicious network connections.

**Hint:** Check the network connections and listening ports on the target system.

**Validation:** The task is considered successful if the student identifies the suspicious port `4444` used for C2 communication.

## TRAINING_LEVEL 2
**Task:** Analyze the systemd services on the target system to identify any suspicious or unauthorized services.

**Objective:** Determine if any unauthorized services are running that could be related to the suspicious network activity.

**Hint:** List all systemd services and check for any services that look suspicious or unauthorized.

**Validation:** The task is considered successful if the student identifies the suspicious service `-bash.service`.

## TRAINING_LEVEL 3
**Task:** Investigate the file transfers between the target system and the next-target system.

**Objective:** Determine if any unauthorized file transfers are occurring between the target system and the next-target system.

**Hint:** Check the logs and systemd services related to file transfers on the target system.

**Validation:** The task is considered successful if the student identifies the service `payload-transfer.service` responsible for the file transfers.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through investigating and responding to a potential Tsunami/Kaiten malware incident.