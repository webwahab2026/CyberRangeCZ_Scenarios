### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Mirai botnet infection within your organization's network. The Mirai botnet is known for turning IoT devices into a botnet for launching distributed denial-of-service (DDoS) attacks. Your goal is to identify and mitigate the botnet activity.

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
While monitoring network traffic, you have noticed unusual outbound connections from one of the hosts. Your task is to identify the service responsible for this suspicious behavior.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check the systemd services and look for any unusual or recently added services.

**Validation:**
The service name should be identified and reported.

### TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Description:**
You have observed a significant increase in network traffic originating from the same host. Your task is to identify the service responsible for this abnormal traffic.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Examine the network connections and look for any services that are generating a high volume of traffic.

**Validation:**
The service name should be identified and reported.

### TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Description:**
You need to understand how the identified suspicious service maintains its persistence on the system. Investigate the persistence mechanism used by the service.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Check the systemd timers and look for any timers associated with the suspicious service.

**Validation:**
The persistence mechanism should be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and mitigation of a Mirai botnet infection, ensuring they develop the necessary skills for incident response.