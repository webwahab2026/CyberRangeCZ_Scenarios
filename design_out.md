### Scenario: Linux/Remaiten Botnet Investigation

**INFO_LEVEL:**
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH

---

**TRAINING_LEVEL 1:**

**Task:**
Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check running services and their network connections.

**Validation:**
The service name must be identified and reported.

---

**TRAINING_LEVEL 2:**

**Task:**
Identify the service responsible for generating abnormal volumes of network traffic.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Examine network connections and service logs for unusual traffic patterns.

**Validation:**
The service name must be identified and reported.

---

**TRAINING_LEVEL 3:**

**Task:**
Determine how the suspicious service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Investigate systemd services and timers.

**Validation:**
The persistence mechanism (service name or persistence identifier) must be identified and reported.

---