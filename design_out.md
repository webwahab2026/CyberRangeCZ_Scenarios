### Scenario: Kobalos Malware Investigation

**INFO_LEVEL:**
The target network has been compromised by the Kobalos malware, a sophisticated Linux backdoor. Your task is to investigate the infection, identify the malicious activity, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the `target` host and identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of active services and look for any that seem unusual or unauthorized.

---

**TRAINING_LEVEL 2: Persistence Discovery**

**Task:**
Determine how the suspicious service identified in the previous task is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine systemd services and timers to find any that might be related to the suspicious service.

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication between the `target` host and the `c2-server`.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to find any unusual or unauthorized communication.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, persistence mechanism, and C2 communication port. The hidden flags for validation are the service name, persistence identifier, and C2 port number.