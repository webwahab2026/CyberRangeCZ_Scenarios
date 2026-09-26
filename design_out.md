### Scenario: ELF_IMEIJ.A Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity, suggesting a potential compromise. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the target system for any unauthorized or suspicious services running. Identify the service that is potentially malicious.

**Hint:**
Check the running services and look for any that seem out of place or unfamiliar.

**Q/A:**
What is the name of the suspicious service?

---

**TRAINING_LEVEL 2: Persistence Discovery**

**Task:**
Determine how the suspicious service is automatically started after a system reboot. Identify the persistence mechanism used.

**Hint:**
Examine systemd services and timers to find how the service is scheduled to run.

**Q/A:**
What is the name of the systemd service or timer responsible for the persistence of the suspicious service?

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Identify the network port used for the suspicious communication between the target system and the potential command-and-control (C2) server.

**Hint:**
Inspect network connections and logs to find the port used for outbound communication.

**Q/A:**
Which network port is used for the suspicious communication?

---