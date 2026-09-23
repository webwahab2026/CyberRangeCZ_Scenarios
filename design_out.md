# Linux/XorDDoS Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns, and initial investigations suggest a potential botnet infection. Your task is to investigate the compromised hosts, identify the botnet components, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that communicates with an external host?

**Hint:** Check the systemd services and look for unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Determine the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server?

**Hint:** Investigate the network connections and logs of the suspicious service identified in the previous task.

## TRAINING_LEVEL 3
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating the malicious network traffic?

**Hint:** Look for services that are not part of the standard system configuration and check their execution logs.

---

**Validation:**

1. **TRAINING_LEVEL 1:**
   - Expected Answer: `bot-beacon.service`
   - Validation: The student's answer should match the service name exactly.

2. **TRAINING_LEVEL 2:**
   - Expected Answer: `192.168.70.5`
   - Validation: The student's answer should match the C2 server's IP address exactly.

3. **TRAINING_LEVEL 3:**
   - Expected Answer: `bot-flood.service`
   - Validation: The student's answer should match the service name exactly.