### Scenario: ELF_IMEIJ Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity and performance degradation. Initial analysis suggests a potential backdoor malware infection. Your task is to investigate, identify, and mitigate the threat.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is reachable at `192.168.50.5`.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the target system and identify any unauthorized or suspicious services running on the host.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the status of all running services and look for any that are not part of the standard system configuration.

---

**TRAINING_LEVEL 2: Persistence Discovery**

**Task:**
Determine how the suspicious service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to find any suspicious configurations.

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to identify any unusual activity.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, persistence mechanism, and C2 communication port. The hidden flags for validation are the service name, persistence identifier, and C2 port number.