### Scenario: Mirai Botnet Investigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Objective:**
Investigate and mitigate a Mirai botnet infection on compromised Linux systems within your network. The botnet is using the Linux/Mirai-Hilix variant to launch DDoS attacks.

**Background:**
Your organization has detected unusual network traffic and potential DDoS attacks originating from internal systems. Initial analysis suggests a Mirai botnet infection. Your task is to investigate the compromised systems, identify the command-and-control (C2) infrastructure, and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Detect and analyze C2 communication.
- Mitigate the botnet infection by containing the threat and removing persistence mechanisms.

---

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious beacon service used for C2 communication.

**Description:**
The compromised systems are communicating with a C2 server. Investigate the system services and identify the beacon service used for C2 communication.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious service related to C2 communication.

**Flag:** bot-beacon-Hilix.sh.service

**Hint:** Look for services with unusual names or descriptions related to system health or updates.

---

#### TRAINING_LEVEL 2
**Task:** Identify the suspicious flood service used for DDoS attacks.

**Description:**
The compromised systems are launching DDoS attacks against a target. Investigate the system services and identify the flood service used for these attacks.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious service related to DDoS attacks.

**Flag:** bot-flood-Hilix.sh.service

**Hint:** Look for services with unusual names or descriptions related to network diagnostics or probes.

---

#### TRAINING_LEVEL 3
**Task:** Remove the persistence mechanism used by the malware.

**Description:**
The malware has established persistence on the compromised systems. Investigate the system and remove the persistence mechanism to prevent reinfection.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all systemd timers using `systemctl list-timers`.
3. Identify and disable the suspicious timer related to the malware's persistence.
4. Remove the timer and its associated service.

**Flag:** system-update-checker.timer

**Hint:** Look for timers with unusual names or descriptions related to system updates or health checks.

---

### Conclusion
By completing these tasks, you will have successfully identified and mitigated the Mirai botnet infection on the compromised systems. Your actions will help contain the threat and prevent further DDoS attacks.