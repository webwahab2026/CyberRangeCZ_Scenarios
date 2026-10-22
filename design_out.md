# Gafgyt Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL
### Task 1: Suspicious Beacon Service Discovery
**Description:**
Investigate the bot1 host and identify any unauthorized or suspicious services responsible for periodic external communication.

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

**Flag Format:**
Each task has a hidden flag that must be submitted in the format `FLAG: <answer>`. The answer should be the exact name of the service or mechanism identified in the task.

**Validation:**
The scenario will validate the submitted flags against the expected answers. Ensure that the answers are derived from the investigation of the bot1 host using the provided credentials.

**Note:**
Do not modify any files or services on the host unless explicitly instructed to do so in a task. This scenario is for investigation purposes only.