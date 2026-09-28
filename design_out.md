### INFO_LEVEL
**Scenario Title:** Rhombus Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Rhombus botnet infection on a Linux-based network. The botnet is known to target VPS and IoT devices, acting as a dropper for additional malware and engaging in DDoS activities. Your goal is to identify and mitigate the botnet activity.

**Learning Objectives:**
- Identify unauthorized or suspicious services responsible for periodic external communication.
- Distinguish malicious traffic generation services from legitimate network services.
- Identify persistence mechanisms used by the botnet.
- Analyze network traffic to identify ports used by botnet communication.
- Determine the target of the flooding activity.
- Collect forensic evidence supporting the identified botnet activity.
- Correlate collected evidence to classify the observed behavior as botnet activity or legitimate system behavior.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Beacon Service Discovery
**Description:**
Investigate the host `bot1` and identify an unauthorized or suspicious service responsible for periodic external communication. This service is likely associated with botnet activity.
**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint:**
Check the systemd services and look for any unusual or recently created services.
**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 2
**Task:** Suspicious Flood Service Discovery
**Description:**
Identify the service responsible for generating abnormal volumes of network traffic on `bot1`. This service is likely part of the botnet's DDoS capabilities.
**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.
**Hint:**
Examine the systemd services and network connections for any suspicious activity.
**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 3
**Task:** Persistence Discovery
**Description:**
Determine how the suspicious service identified in the previous tasks is automatically started after reboot on `bot1`.
**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint:**
Investigate the systemd timers and services for any persistence mechanisms.
**Validation:**
The persistence mechanism (service name or persistence identifier) must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.