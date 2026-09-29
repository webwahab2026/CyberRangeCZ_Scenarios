### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate and respond to this incident. The Fysbis backdoor is a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of Executable and Linking Format (ELF) binaries. Fysbis can install itself to a victim system with or without root privileges.

**ACCESS_LEVEL:**
You have access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can SSH into the `next-target` host using the same credentials.

---

**TRAINING_LEVEL 1:**

**Task:**
Investigate the `target` host and identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---

**TRAINING_LEVEL 2:**

**Task:**
Determine how the suspicious service identified in the previous task is automatically started after a reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to see how the service is configured to start automatically.

**Validation:**
The hidden flag is the name of the systemd service or persistence identifier.

---

**TRAINING_LEVEL 3:**

**Task:**
Identify the process responsible for the suspicious activity on the `target` host.

**Learning Objective:**
Analyze running processes and correlate them with services and network connections.

**Hint:**
Use process monitoring tools to identify any unusual processes and their associated network connections.

**Validation:**
The hidden flag is the name of the suspicious process.