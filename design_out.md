### Scenario: Android Implant Investigation

**INFO_LEVEL:**
The victim host in your network has been compromised by an Android implant known as HackingTeam. This spyware is capable of data exfiltration, screen recording, audio recording, and executing code from downloaded dex files. Your task is to investigate the compromise, identify the indicators of compromise (IOCs), and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.100.10`.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer used for data collection.
**Description:** Investigate the systemd timers on the victim host to identify any suspicious scheduled tasks that might be related to the spyware.
**Hint:** Look for timers that are not part of the standard system configuration.
**Flag:** timer name

**TRAINING_LEVEL 2:**
**Task:** Identify the captured keystroke log file.
**Description:** Search the victim host for any files that might contain captured keystrokes. These files could be used by the spyware to exfiltrate sensitive information.
**Hint:** Check hidden directories and files that are not typically part of the system configuration.
**Flag:** file name

**TRAINING_LEVEL 3:**
**Task:** Identify the data exfiltration mechanism.
**Description:** Investigate the network communication on the victim host to identify any suspicious outbound connections that might be used for data exfiltration.
**Hint:** Look for connections to unexpected IP addresses or ports.
**Flag:** script name

---

**INFO_LEVEL:**
The victim host has been compromised by the HackingTeam Android implant. This spyware is capable of data exfiltration, screen recording, audio recording, and executing code from downloaded dex files. Your task is to investigate the compromise, identify the indicators of compromise (IOCs), and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.100.10`.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer used for data collection.
**Description:** Investigate the systemd timers on the victim host to identify any suspicious scheduled tasks that might be related to the spyware.
**Hint:** Look for timers that are not part of the standard system configuration.
**Flag:** timer name

**TRAINING_LEVEL 2:**
**Task:** Identify the captured keystroke log file.
**Description:** Search the victim host for any files that might contain captured keystrokes. These files could be used by the spyware to exfiltrate sensitive information.
**Hint:** Check hidden directories and files that are not typically part of the system configuration.
**Flag:** file name

**TRAINING_LEVEL 3:**
**Task:** Identify the data exfiltration mechanism.
**Description:** Investigate the network communication on the victim host to identify any suspicious outbound connections that might be used for data exfiltration.
**Hint:** Look for connections to unexpected IP addresses or ports.
**Flag:** script name