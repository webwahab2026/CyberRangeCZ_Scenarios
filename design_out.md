### Scenario: Octopus-Rex Botnet Investigation

**INFO_LEVEL:**
The Octopus-Rex botnet is a multi-task botnet capable of various malicious activities including command and control (C2) communication, lateral movement, exfiltration, and persistence mechanisms. It primarily targets Linux platforms. Your task is to investigate and mitigate the botnet activity within the provided sandbox environment.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the following credentials:
- Username: ubuntu
- Password: ubuntu

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.
**Objective:** Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint:** Check the systemd services and look for any unusual or unfamiliar services.
**Validation:** The service name must be identified and reported.

**TRAINING_LEVEL 2:**
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.
**Objective:** Distinguish malicious traffic generation services from legitimate network services.
**Hint:** Examine the network connections and look for any services that are generating excessive traffic.
**Validation:** The service name must be identified and reported.

**TRAINING_LEVEL 3:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint:** Investigate the systemd timers and look for any timers associated with the suspicious service.
**Validation:** The persistence mechanism must be identified and reported.

---

**Note:** The scenario is designed to align strictly with the provided sandbox environment and MISP event. All tasks are feasible within the given topology and Ansible configuration, and no additional hosts, services, or indicators are invented. The tasks require students to investigate and discover the required information through system, process, service, log, and network analysis.