# Hajime Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL
### Task 1: Suspicious Beacon Service Discovery
**Description:**
Investigate the victim host for any unauthorized or suspicious services that might be responsible for periodic external communication.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check running services and systemd timers for any unusual activity.

### Task 2: Suspicious Flood Service Discovery
**Description:**
Identify the service responsible for generating abnormal volumes of network traffic on the victim host.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Examine systemd services and timers for any unusual network activity.

### Task 3: Persistence Discovery
**Description:**
Determine how the suspicious service is automatically started after reboot on the victim host.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:**
Look for systemd services and timers that might be related to the suspicious activity.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious services and persistence mechanisms as described in the tasks. The hidden flags for validation are the service names and persistence identifiers.