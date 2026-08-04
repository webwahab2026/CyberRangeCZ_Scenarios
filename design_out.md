### Scenario: ELF_IMEIJ Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the ELF_IMEIJ.A backdoor malware. This malware exploits a vulnerability in AVTech devices to execute command injection, triggering the malware download. It gathers system information and network activity data, executes shell commands from the malicious actor, initiates DDoS attacks, and can terminate itself. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the `target` host and identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

---

**TRAINING_LEVEL 2: Persistence Discovery**

**Task:**
Determine how the suspicious service identified in the previous task is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to see how the service is configured to start automatically.

---

**TRAINING_LEVEL 3: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication between the `target` host and the `c2-server`.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Check the network connections and listen ports on the `target` host to identify any unusual or unexpected ports.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, persistence mechanism, and C2 communication port. The hidden flags for validation are the service name, persistence identifier, and C2 port number.