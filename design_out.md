### Scenario: Android Implant Investigation

**INFO_LEVEL:**
This scenario focuses on investigating an Android implant known as "HackingTeam" spyware. The malware is designed to spy on Android devices, collect sensitive information, and exfiltrate data to a command and control (C2) server. Your task is to analyze the compromised system, identify the malware's behavior, and mitigate the threat.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is part of a network that includes a spy server and a colleague host. You can use standard Linux commands and tools to investigate the system.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service used for data exfiltration.
**Description:** The malware has a data exfiltration mechanism that sends collected data to a C2 server. Investigate the system services to identify the suspicious service responsible for this exfiltration.
**Hint:** Check the systemd services and look for any unusual services that might be related to data exfiltration.
**Flag:** exfil_service_unit (e.g., `sys-telemetry.service`)

**TRAINING_LEVEL 2:**
**Task:** Identify the keylogging mechanism used by the malware.
**Description:** The malware includes a keylogging feature that captures user keystrokes. Investigate the system to find the file or script responsible for this keylogging activity.
**Hint:** Look for any unusual scripts or files in the user's home directory or system directories that might be capturing keystrokes.
**Flag:** keylog_path (e.g., `/var/lib/.monitor/keylog.log`)

**TRAINING_LEVEL 3:**
**Task:** Identify the suspicious outbound IP communication used for exfiltration.
**Description:** The malware communicates with a C2 server to exfiltrate collected data. Investigate the network connections to identify the suspicious IP address and port used for this communication.
**Hint:** Use network monitoring tools to check for any unusual outbound connections.
**Flag:** spy_host and spy_port (e.g., `spy-server:443`)

This scenario provides a structured approach to investigating and mitigating the HackingTeam Android implant. By following the tasks and hints, you will gain valuable experience in incident response and malware analysis.