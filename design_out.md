### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
The network has been experiencing unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues. The network consists of several Linux-based systems, including a command-and-control server (c2-server), two potential compromised hosts (bot1 and bot2), and a victim server (victim). All systems are running Ubuntu Noble.

**ACCESS_LEVEL:**
You have SSH access to the entry host bot1 with the following credentials:
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service communicating with the C2 server.
**Description:** Investigate the services running on bot1 and identify the service responsible for beaconing to the C2 server.
**Hint:** Check the systemd services and look for any unusual or recently created services.
**Flag:** bot-beacon-Hilix.sh.service

**TRAINING_LEVEL 2:**
**Task:** Identify the suspicious flood service responsible for the DDoS attacks.
**Description:** Examine the services on bot1 and find the service that is generating flood traffic.
**Hint:** Look for services related to network diagnostics or similar descriptions.
**Flag:** bot-flood-Hilix.sh.service

**TRAINING_LEVEL 3:**
**Task:** Identify and remove the persistence mechanism used by the malware.
**Description:** Investigate the systemd timers and services to find and remove the persistence mechanism that ensures the malware runs after reboots.
**Hint:** Check the systemd timers and look for any suspicious timers that might be related to the malware.
**Flag:** system-update-checker.timer

---

**Validation:**

**TRAINING_LEVEL 1:**
- The service name "bot-beacon-Hilix.sh.service" must be identified as the suspicious beacon service.

**TRAINING_LEVEL 2:**
- The service name "bot-flood-Hilix.sh.service" must be identified as the suspicious flood service.

**TRAINING_LEVEL 3:**
- The timer name "system-update-checker.timer" must be identified and removed as the persistence mechanism.

---

**Debriefing:**

**Summary:**
In this scenario, you investigated a network compromised by the Mirai botnet variant Linux/Mirai-Hilix. You identified the beacon service communicating with the C2 server, the flood service responsible for DDoS attacks, and the persistence mechanism ensuring the malware's continued operation.

**Lessons Learned:**
1. **Beacon Identification:** Understanding how to identify suspicious beacon services is crucial for detecting command-and-control communications.
2. **Flood Service Detection:** Recognizing flood services helps in mitigating DDoS attacks and understanding the attack vectors.
3. **Persistence Mechanisms:** Identifying and removing persistence mechanisms is essential for ensuring that malware does not persist after initial infection.

**Recommendations:**
1. **Regular Monitoring:** Implement regular monitoring of network traffic and system services to detect unusual activities.
2. **Security Updates:** Keep all systems updated with the latest security patches to prevent known vulnerabilities from being exploited.
3. **Access Controls:** Enforce strong access controls and use complex passwords to prevent brute-force attacks.

---

This scenario provides a practical exercise in investigating and mitigating a Mirai botnet infection, focusing on identifying key components of the malware and understanding its behavior.