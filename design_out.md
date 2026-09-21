# Gafgyt Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL
### Task 1: Suspicious Beacon Service Discovery
**Objective:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check the systemd services and look for any unusual or recently created services.

### Task 2: Suspicious Flood Service Discovery
**Objective:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service responsible for generating abnormal volumes of network traffic?

**Hint:** Investigate the systemd services and look for any services that might be related to network diagnostics or probes.

### Task 3: C2 Communication Discovery (IP Address)
**Objective:** Determine the external host communicating with the compromised system.

**Question:** What is the IP address of the external host communicating with the compromised system?

**Hint:** Examine the network connections and logs to identify the command-and-control server.

---

**Validation:**

1. **Task 1:** The hidden flag is the name of the suspicious service responsible for periodic external communication.
2. **Task 2:** The hidden flag is the name of the service responsible for generating abnormal volumes of network traffic.
3. **Task 3:** The hidden flag is the IP address of the external host communicating with the compromised system.

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging investigation exercise.