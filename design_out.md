### INFO_LEVEL
**Scenario Title:** Rhombus Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Rhombus botnet infection on a Linux-based network. The botnet is known to target VPS and IoT devices, performing DDoS attacks and communicating with command-and-control (C2) servers. Your goal is to identify and mitigate the botnet activity.

**Learning Objectives:**
- Identify unauthorized or suspicious services responsible for periodic external communication.
- Determine the persistence mechanisms used by the botnet.
- Analyze network traffic to identify ports used by botnet communication.
- Collect forensic evidence supporting the identified botnet activity.
- Assess whether the observed activity is malicious or benign.
- Block communication between the compromised host and the external C2 server.
- Stop the malicious network flooding while minimizing disruption to legitimate traffic.
- Safely terminate malicious execution while minimizing impact on legitimate services.
- Remove the persistence mechanism used by the malicious service.
- Remove the malicious executable and associated artifacts from the compromised system.
- Verify that the botnet has been successfully removed and that no malicious communication or attack traffic remains.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Description:**
On the entry host (bot1), investigate the running services and identify any unauthorized or suspicious services that are responsible for periodic external communication. This could indicate beaconing behavior associated with botnet activity.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check the systemd services and look for any unusual or unauthorized services.

**Validation:**
The service name must be identified and reported.

### TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Description:**
Investigate the persistence mechanisms used by the suspicious service identified in the previous task. Determine how the service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Examine the systemd timers and services to find any persistence mechanisms.

**Validation:**
The persistence mechanism (service name or persistence identifier) must be identified and reported.

### TRAINING_LEVEL 3
**Task:** Collect forensic evidence supporting the identified botnet activity.

**Description:**
Gather relevant logs, service information, process details, and network evidence demonstrating beaconing or flooding behavior. This evidence will support the identification of the botnet activity.

**Learning Objective:**
Collect relevant logs, service information, process details, and network evidence demonstrating botnet activity.

**Hint:**
Check the system logs and network traffic to gather evidence.

**Validation:**
The collected evidence set must be reported and validated.