### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and identify the source of these issues.

**ACCESS_LEVEL:**
- Entry Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.
**Objective:** Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint:** Check running services and their network connections.
**Validation:** Service name

**TRAINING_LEVEL 2:**
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.
**Objective:** Distinguish malicious traffic generation services from legitimate network services.
**Hint:** Examine network traffic patterns and service logs.
**Validation:** Service name

**TRAINING_LEVEL 3:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint:** Investigate system startup configurations and scheduled tasks.
**Validation:** Service name or persistence identifier

---

### Explanation

**INFO_LEVEL:**
This section provides a general overview of the issue, prompting the investigator to look into unusual traffic patterns and potential unauthorized access.

**ACCESS_LEVEL:**
The entry point is bot1, with the provided credentials. Access is via SSH, which is a common method for investigating Linux-based systems.

**TRAINING_LEVEL 1:**
The task focuses on identifying a suspicious service responsible for periodic external communication. This aligns with the Mirai botnet's behavior of beaconing to a C2 server. The hint guides the investigator to check running services and their network connections, which is a standard approach in incident response.

**TRAINING_LEVEL 2:**
This task targets the service generating abnormal network traffic, which is characteristic of a DDoS attack. The hint suggests examining network traffic patterns and service logs, which are essential for identifying malicious activities.

**TRAINING_LEVEL 3:**
The task involves finding the persistence mechanism used by the malicious service. The hint directs the investigator to look into system startup configurations and scheduled tasks, which are common persistence methods in Linux environments.

Each task is designed to be feasible within the provided sandbox environment, using only the hosts, services, and network topology that are explicitly defined. The tasks encourage investigation and discovery rather than providing direct answers, aligning with the Incident Response profile and the Mirai botnet's behavior described in the MISP event.