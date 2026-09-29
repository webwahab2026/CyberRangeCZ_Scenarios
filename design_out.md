### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate and respond to this incident. The Fysbis backdoor is a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of ELF binaries and can install itself with or without root privileges.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can SSH to `next-target` using the same credentials.

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

**TRAINING_LEVEL 3: Lateral Movement Investigation**

**Task:**
Identify any file transfers or remote execution used to move between hosts from the `target` to the `next-target`.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Hint:**
Check the logs and systemd timers for any scripts or services that transfer files between hosts.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, its persistence mechanism, and the lateral movement method used by the attacker. The hidden flags for validation are the service name, persistence identifier, and the script used for lateral movement.