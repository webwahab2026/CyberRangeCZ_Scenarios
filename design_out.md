# Mirai Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL
### Task 1: Suspicious Beacon Service Discovery
**Description:**
Investigate the bot1 host and identify any unauthorized or suspicious services that are responsible for periodic external communication.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check the systemd services and look for any unusual or recently created services.

### Task 2: Suspicious Flood Service Discovery
**Description:**
Identify the service responsible for generating abnormal volumes of network traffic on the bot1 host.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Examine the systemd timers and services for any that might be related to network diagnostics or probes.

### Task 3: Persistence Discovery
**Description:**
Determine how the suspicious service identified in Task 1 is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Look for systemd timers or other scheduled tasks that might be responsible for starting the suspicious service.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious services and their persistence mechanisms. The hidden flags for validation are the service names and persistence identifiers.