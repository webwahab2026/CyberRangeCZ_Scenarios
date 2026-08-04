### Scenario: Sednit Backdoor Investigation

**INFO_LEVEL:**
The Sednit group is known for using sophisticated malware to compromise networks. In this scenario, you will investigate a compromised host that exhibits signs of Sednit backdoor activity. Your goal is to identify and mitigate the threat.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the host and perform necessary actions to contain and eradicate the threat.

---

**TRAINING_LEVEL 1:**

**Task:**
Investigate the `target` host and identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

---

**TRAINING_LEVEL 2:**

**Task:**
Determine how the suspicious service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Examine the systemd service files and timers to understand how the service maintains persistence.

---

**TRAINING_LEVEL 3:**

**Task:**
Identify the process responsible for suspicious activity on the host.

**Learning Objective:**
Analyze running processes and correlate them with services and network connections.

**Hint:**
Use process monitoring tools to identify the process associated with the suspicious service.

---

**Validation:**
The scenario will be validated based on the correct identification of the suspicious service, persistence mechanism, and process responsible for the suspicious activity. The hidden flags for validation are the service name, persistence identifier, and process name.