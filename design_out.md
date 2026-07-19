### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The target host has been compromised by the BRICKSTORM backdoor. Your task is to investigate the compromise, identify the persistence mechanisms, and trace the command-and-control (C2) communication.

#### ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. The target host is `192.168.50.5`.

---

### TRAINING_LEVEL 1
**Task:** Identify the suspicious service running on the target host.

**Description:**
Investigate the running services on the target host to identify any suspicious services that might be related to the BRICKSTORM backdoor.

**Hint:**
Check the systemd services and look for any unusual or unfamiliar services.

**Flag:**
The flag is the name of the suspicious service.

---

### TRAINING_LEVEL 2
**Task:** Identify the persistence mechanism used by the suspicious service.

**Description:**
Examine the persistence mechanisms used by the suspicious service to maintain its presence on the target host.

**Hint:**
Look for systemd timers or services that might be responsible for the persistence of the suspicious service.

**Flag:**
The flag is the name of the persistence mechanism (e.g., systemd service or timer name).

---

### TRAINING_LEVEL 3
**Task:** Identify the outbound C2 communication.

**Description:**
Trace the outbound network connections from the target host to identify any C2 communication with the attacker's server.

**Hint:**
Check the network connections and look for any unusual or suspicious outbound connections.

**Flag:**
The flag is the IP address and port of the C2 server.

---

### Summary
This scenario provides a realistic post-compromise environment where participants must investigate active services, running processes, scheduled tasks, and network connections to reconstruct the attack chain. The scenario is designed to align with the provided MISP event, sandbox topology, and security profile, ensuring a coherent and challenging exercise for incident response professionals.