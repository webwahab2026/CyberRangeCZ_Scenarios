### Scenario: Mirai Botnet Investigation and Mitigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation and Mitigation

**Objective:**
Investigate and mitigate a Mirai botnet infection targeting Realtek and Huawei routers. The botnet is using the Linux/Mirai-Hilix variant, which exploits default passwords to gain access to devices and performs lateral movement, exfiltration, and maintains persistence.

**Background:**
You are part of an incident response team tasked with investigating and mitigating a Mirai botnet infection. The botnet is using the Linux/Mirai-Hilix variant, which targets Realtek and Huawei routers. The malware performs lateral movement, exfiltration, and maintains persistence through various mechanisms.

**Learning Objectives:**
- Identify and investigate suspicious beacon and flood services.
- Identify and mitigate persistence mechanisms.
- Contain and block C2 communication and flooding activities.

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Identify and investigate suspicious beacon service
**Description:**
Investigate the suspicious beacon service running on bot1. The service is communicating with a command-and-control (C2) server. Identify the service name and provide it as the flag.
**Hint:** Check the systemd services running on the host.
**Flag:** bot-beacon-Hilix.sh.service

#### TRAINING_LEVEL 2
**Task:** Identify and investigate suspicious flood service
**Description:**
Investigate the suspicious flood service running on bot1. The service is performing flooding attacks. Identify the service name and provide it as the flag.
**Hint:** Check the systemd services running on the host.
**Flag:** bot-flood-Hilix.sh.service

#### TRAINING_LEVEL 3
**Task:** Contain and block C2 communication
**Description:**
Contain and block the C2 communication by stopping the beacon service on bot1. Identify the port number used for C2 communication and provide it as the flag.
**Hint:** Check the beacon service configuration.
**Flag:** 2222