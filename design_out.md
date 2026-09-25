# KAITEN Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Host: victim
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL
### Task 1: Suspicious Beacon Service Discovery
**Description:**
Investigate the system to identify any unauthorized or suspicious services responsible for periodic external communication.

**Learning Objective:**
Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:**
Check running services and their network connections.

### Task 2: Suspicious Flood Service Discovery
**Description:**
Identify the service responsible for generating abnormal volumes of network traffic.

**Learning Objective:**
Distinguish malicious traffic generation services from legitimate network services.

**Hint:**
Examine systemd timers and services for unusual network activity.

### Task 3: C2 Communication Discovery (Port)
**Description:**
Determine which network port is used for suspicious command-and-control communication.

**Learning Objective:**
Analyze network traffic to identify ports used by botnet communication.

**Hint:**
Inspect network connections and logs for unusual outbound traffic.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious services and the C2 communication port. The hidden flags for validation are:
- Service name for beaconing activity
- Service name for flooding activity
- C2 port number

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.