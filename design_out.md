### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
The network has been experiencing unusual traffic patterns and performance degradation. Initial investigations suggest a possible botnet infection. Your task is to investigate and contain the threat.

**ACCESS_LEVEL:**
- Entry Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service communicating with the C2 server.
**Description:** Investigate the services running on bot1 and identify the service responsible for beaconing to the C2 server.
**Hint:** Check the systemd services and look for any unusual or recently created services.
**Flag:** bot-beacon-Hilix.sh.service

**TRAINING_LEVEL 2:**
**Task:** Identify the suspicious flood service responsible for the DDoS attacks.
**Description:** Examine the systemd services on bot1 and find the service that is generating flood traffic.
**Hint:** Look for services related to network diagnostics or similar descriptions.
**Flag:** bot-flood-Hilix.sh.service

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication by blocking the suspicious port.
**Description:** Identify the port used for C2 communication and block it to prevent further beaconing.
**Hint:** Check the beacon service configuration for the port number.
**Flag:** 2222