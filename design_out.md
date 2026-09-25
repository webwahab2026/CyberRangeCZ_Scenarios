# Supreme Backdoor Factory Incident Response Scenario

## INFO_LEVEL
The organization has detected suspicious network activity originating from the target host (192.168.50.5). Initial analysis suggests potential compromise by the Supreme Backdoor malware family. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host (192.168.50.5) with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring network traffic, you noticed unusual outbound connections from the target host. Investigate these connections to identify any suspicious activity.
**Hint:** Check active network connections and review system logs for unusual outbound traffic patterns.
**Validation:** The task is considered successful if the student identifies the suspicious port (4444) used for outbound connections.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanisms
**Description:** The suspicious service appears to be persisting across reboots. Investigate how this service is being automatically started and determine the persistence method.
**Hint:** Examine systemd services and timers that might be responsible for starting the suspicious service.
**Validation:** The task is considered successful if the student identifies the systemd timer (lab-checkin.timer) responsible for the suspicious service.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** There is evidence suggesting that the attacker might be attempting to move laterally within the network. Investigate the target host for any signs of lateral movement activity.
**Hint:** Review system logs and check for any unusual file transfers or remote execution commands.
**Validation:** The task is considered successful if the student identifies the payload-transfer.service responsible for lateral movement activity.