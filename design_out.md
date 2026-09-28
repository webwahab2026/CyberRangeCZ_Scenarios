# Scenario: CDRThief Investigation

## INFO_LEVEL
The VoIP platform has been experiencing unusual network activity. As an incident responder, your task is to investigate and contain the threat. The primary system under investigation is the target host (192.168.50.5), which is running a Linknat VOS2009 softswitch. You have access to the system as user 'cyrano' with password 'cyrano'.

## ACCESS_LEVEL
1. Entry host: target (192.168.50.5)
2. Username: cyrano
3. Password: cyrano
4. Access method: SSH

## TRAINING_LEVEL 1
**Task:** Investigate unusual network connections
**Description:** While monitoring the target system, you noticed unusual outbound network connections. Investigate these connections to identify any suspicious activity.
**Hint:** Check the system logs for recent network connections and look for any unusual destinations or patterns.
**Validation:** The task is considered successful if the student identifies the suspicious connection to the C2 server (192.168.40.5) on port 4444.

## TRAINING_LEVEL 2
**Task:** Analyze suspicious process
**Description:** You've identified a suspicious network connection. Now, investigate the process responsible for this connection. Determine its behavior and any associated files.
**Hint:** Use process investigation tools to analyze the suspicious process and its network activity.
**Validation:** The task is considered successful if the student identifies the process name and its associated files, including any unusual file paths or behaviors.

## TRAINING_LEVEL 3
**Task:** Investigate data exfiltration
**Description:** Evidence suggests that sensitive data might be exfiltrated from the system. Investigate the system to find any evidence of data exfiltration.
**Hint:** Check for any unusual file transfers or network traffic that might indicate data exfiltration.
**Validation:** The task is considered successful if the student identifies evidence of data exfiltration, such as unusual file transfers or network traffic to the C2 server.