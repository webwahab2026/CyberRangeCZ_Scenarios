### Scenario: Linux/AirDropBot Botnet Investigation

**INFO_LEVEL:**
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues. The network consists of several Linux-based systems, including a command-and-control server, compromised bots, and a victim system. Use the provided access credentials to log in to the systems and perform your investigation.

**ACCESS_LEVEL:**
- **Entry Host:** bot1
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.
**Objective:** Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint:** Check the systemd services and look for any unusual or recently created services.
**Validation:** The service name must be identified and reported.

**TRAINING_LEVEL 2:**
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.
**Objective:** Distinguish malicious traffic generation services from legitimate network services.
**Hint:** Examine the network connections and look for any services that are generating excessive traffic.
**Validation:** The service name must be identified and reported.

**TRAINING_LEVEL 3:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint:** Investigate the systemd timers and services to find any persistence mechanisms.
**Validation:** The persistence mechanism (service name or persistence identifier) must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Linux/AirDropBot botnet, focusing on identifying suspicious services, abnormal network traffic, and persistence mechanisms. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the strict constraints provided.