### Scenario: Xbash Botnet Investigation

**INFO_LEVEL:**
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these incidents. The network consists of several Ubuntu servers, including a command-and-control (C2) server, two compromised bots, and a victim server. The compromised hosts are running the Xbash botnet, which combines botnet, ransomware, and coinmining capabilities. The botnet uses multiple C2 domains and IPs for communication and can download additional payloads.

**ACCESS_LEVEL:**
- **Entry Host:** bot1
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.
**Objective:** Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint:** Check the systemd services and look for any unusual or recently created services.
**Validation:** The service name must be identified and investigated.

**TRAINING_LEVEL 2:**
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.
**Objective:** Distinguish malicious traffic generation services from legitimate network services.
**Hint:** Examine the network connections and look for any services that are generating excessive traffic.
**Validation:** The service name must be identified and investigated.

**TRAINING_LEVEL 3:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint:** Check the systemd timers and look for any timers associated with the suspicious service.
**Validation:** The persistence mechanism must be identified and investigated.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.