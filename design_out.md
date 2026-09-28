### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Mirai botnet infection within your organization's network. The Mirai botnet targets IoT devices and Linux systems, using them to perform DDoS attacks. Your goal is to identify and mitigate the botnet activity.

**Learning Objectives:**
- Identify unauthorized or suspicious services responsible for periodic external communication.
- Distinguish malicious traffic generation services from legitimate network services.
- Identify persistence mechanisms used by the botnet.
- Analyze network traffic to identify ports used by botnet communication.
- Determine the victim of the flooding activity.
- Collect forensic evidence supporting the identified botnet activity.
- Correlate collected evidence to classify the observed behavior as botnet activity or legitimate system behavior.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Description:**
While monitoring network traffic, you noticed unusual outbound connections from `bot1`. Investigate the system to identify any unauthorized or suspicious services that might be responsible for this behavior.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check the systemd services and timers to identify any suspicious activities.

**Validation:**
The service name should be identified as `bot-beacon.timer`.

### TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Description:**
Further investigation revealed that `bot1` is generating an abnormal volume of network traffic. Identify the service responsible for this activity.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Look for services that are not part of the standard system configuration and have unusual names.

**Validation:**
The service name should be identified as `bot-flood.timer`.

### TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Description:**
You have identified the suspicious services but need to understand how they persist after a system reboot. Investigate the persistence mechanism used by these services.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Examine the systemd timers and services to find the persistence mechanism.

**Validation:**
The persistence mechanism should be identified as `system-update-checker.timer`.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.