# XOR.DDoS Incident Response Scenario

## INFO_LEVEL
The organization has detected unusual network activity on its Linux servers. Initial analysis suggests a potential compromise by the XOR.DDoS malware family, specifically the Groundhog backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target server with the username `cyrano` and password `cyrano`. The target server's IP address is `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Activity
**Description:** You have noticed unusual outbound network connections from the target server. Investigate these connections to identify any suspicious activity.
**Hint:** Check the network connections and recent logs for any unusual patterns.
**Validation:** The task is considered successful if the student identifies the suspicious port and the destination IP address.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanism
**Description:** Determine how the suspicious activity is maintained across reboots. Identify the persistence mechanism used by the malware.
**Hint:** Look for systemd services or cron jobs that might be related to the suspicious activity.
**Validation:** The task is considered successful if the student identifies the systemd service unit file associated with the suspicious activity.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** Check for any evidence of lateral movement from the target server to other hosts in the network.
**Hint:** Examine logs and system configurations for any signs of remote access or file transfers.
**Validation:** The task is considered successful if the student identifies the service responsible for lateral movement and the destination host.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is structured to guide the student through the investigation and response process while adhering to the constraints and requirements specified.