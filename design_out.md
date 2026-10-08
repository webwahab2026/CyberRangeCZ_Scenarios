### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The organization has detected unusual network activity originating from the target host. Initial analysis suggests a potential compromise involving the Sofacy group's Fysbis backdoor. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. The target host has IP address `192.168.50.5`.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the target host and identify any unauthorized or suspicious services running on the system.

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
Examine systemd services and timers to find any that are related to the suspicious service.

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports to find any unusual activity.

---