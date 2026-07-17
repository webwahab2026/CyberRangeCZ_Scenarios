### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
The scenario simulates a Mirai botnet infection targeting Realtek and Huawei routers. The botnet establishes a command-and-control (C2) infrastructure and performs DDoS attacks. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service communicating with the C2 server.
**Description:** Investigate the services running on bot1 and identify the service responsible for beaconing to the C2 server.
**Hint:** Check the systemd services and look for any unusual services.
**Flag:** bot-beacon-Hilix.x86.elf.service

**TRAINING_LEVEL 2:**
**Task:** Identify the suspicious flood service performing DDoS attacks.
**Description:** Investigate the services running on bot1 and identify the service responsible for performing DDoS attacks.
**Hint:** Check the systemd services and look for any unusual services.
**Flag:** bot-flood-Hilix.x86.elf.service

**TRAINING_LEVEL 3:**
**Task:** Identify the persistence mechanism used by the malware.
**Description:** Investigate the systemd services and timers on bot1 to identify any persistence mechanisms used by the malware.
**Hint:** Check the systemd timers and look for any unusual timers.
**Flag:** system-update-checker.timer