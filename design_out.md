### Scenario: Sofacy Fysbis Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity. Your task is to investigate and identify the source of this activity, determine its nature, and take appropriate action to contain and remediate the threat.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and has the IP address `192.168.50.5`.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the target system and identify any unauthorized or suspicious services running on the host.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the status of all services and look for any that are not part of the standard system configuration.

---

**TRAINING_LEVEL 2: Persistence Discovery**

**Task:**
Determine how the suspicious service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to find any that are related to the suspicious service.

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to find any that are associated with the suspicious service.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, its persistence mechanism, and the network port used for communication. The hidden flags for validation are the service name, persistence identifier, and C2 port number.