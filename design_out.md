### Scenario: ELF_IMEIJ Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the ELF_IMEIJ.A backdoor malware. This malware is known to exploit vulnerabilities in AVTech devices, execute command injections, gather system information, and initiate DDoS attacks. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any lateral movement to the `next-target` host.

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
Examine the systemd service files and timers to understand how the service is maintained.

---

**TRAINING_LEVEL 3: Lateral Movement Investigation**

**Task:**
Identify any file transfers or remote execution used to move between hosts from the `target` to the `next-target` host.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Hint:**
Check the logs and systemd services related to file transfers and remote execution.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, its persistence mechanism, and the evidence of lateral movement. The hidden flags for validation are the service name, persistence identifier, and the destination host for lateral movement.