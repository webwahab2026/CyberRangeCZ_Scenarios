### Scenario: Mirai Botnet Investigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Objective:**
Investigate and mitigate a Mirai botnet infection targeting Realtek and Huawei routers. The botnet is using a variant called Linux/Mirai-Hilix, which exploits vulnerabilities in these routers to perform DDoS attacks.

**Background:**
You are part of an incident response team tasked with investigating and mitigating a Mirai botnet infection. The botnet is using a variant called Linux/Mirai-Hilix, which targets Realtek and Huawei routers. The botnet uses a new TABLE encoder and aims to exploit vulnerabilities in these routers to gain control and perform DDoS attacks.

**Learning Objectives:**
- Identify and investigate suspicious beacon services.
- Identify and investigate suspicious flood services.
- Identify and investigate persistence mechanisms.
- Identify and investigate suspicious outbound/Inbound IP and Port.
- Identify flood attack victim.
- Contain/Block C2 communication.
- Contain/Block Flooding.
- Kill suspicious service.
- Remove persistence.

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH
**Privilege Boundaries:** User-level access

#### TRAINING_LEVEL 1
**Task:** Identify and investigate suspicious beacon service.

**Description:**
Investigate the suspicious beacon service running on bot1. This service is communicating with a command-and-control (C2) server.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious beacon service.
4. Investigate the service by checking its configuration and logs.

**Flag:** bot-beacon-Hilix.sh.service

**Validation:**
The flag should be the name of the suspicious beacon service.

**Hint:**
Look for services related to system health or updates.

#### TRAINING_LEVEL 2
**Task:** Identify and investigate suspicious flood service.

**Description:**
Investigate the suspicious flood service running on bot1. This service is performing DDoS attacks on a target host.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious flood service.
4. Investigate the service by checking its configuration and logs.

**Flag:** bot-flood-Hilix.sh.service

**Validation:**
The flag should be the name of the suspicious flood service.

**Hint:**
Look for services related to network diagnostics or probes.

#### TRAINING_LEVEL 3
**Task:** Contain/Block C2 communication.

**Description:**
Contain the C2 communication by blocking the suspicious outbound port used by the beacon service.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. Identify the outbound port used by the beacon service.
3. Block the port using `iptables` or a similar tool.

**Flag:** 2222

**Validation:**
The flag should be the port number used by the beacon service.

**Hint:**
Check the service configuration for the port number.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the user through identifying and mitigating the Mirai botnet infection while adhering to the sandbox constraints and using only the indicators present in the MISP event.