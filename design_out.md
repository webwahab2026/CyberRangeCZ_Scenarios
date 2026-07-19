### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host infected with the Kobalos malware. Your goal is to identify persistence mechanisms, detect command-and-control (C2) communication, and trace lateral movement to other hosts in the network.

**Learning Objectives:**
- Identify persistence mechanisms hidden in systemd services and timers
- Detect active network listeners and outbound C2 connections
- Trace lateral movement via SSH and rsync
- Analyze shell scripts deployed as malware payloads
- Correlate log evidence across multiple hosts

---

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service
**Description:**
Investigate the running services on the target host. Identify the suspicious service that is listening on port 8080 and serving the contents of the inventory log file.
**Flag:** lab-checkin-listener.service

**Hint:**
Check the systemd services running on the target host and look for any services listening on port 8080.

---

### TRAINING_LEVEL 2
**Task:** Identify Service Persistence Mechanism
**Description:**
Determine how the suspicious service identified in Task 1 is maintained on the system. Identify the persistence mechanism used to ensure the service starts automatically.
**Flag:** local-inventory.timer

**Hint:**
Examine the systemd timers and services to find the persistence mechanism for the suspicious service.

---

### TRAINING_LEVEL 3
**Task:** Identify Data Exfiltration
**Description:**
Analyze the network connections and logs to identify the data exfiltration mechanism. Determine the file being exfiltrated and the destination IP address.
**Flag:** inventory.log

**Hint:**
Check the network connections and logs on the target host to identify the data exfiltration mechanism.