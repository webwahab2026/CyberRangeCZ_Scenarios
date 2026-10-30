### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target network has been compromised by the Sofacy group using the Fysbis Linux backdoor. Your task is to investigate and respond to this incident. The Fysbis malware is a modular Linux backdoor that implements plug-in and controller modules as distinct classes. It can install itself with or without root privileges, increasing the options available to an adversary when selecting accounts for installation. The malware includes both 32-bit and 64-bit versions of ELF binaries.

**ACCESS_LEVEL:**
You have access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can SSH to `next-target` using the same credentials.

---

**TRAINING_LEVEL 1:**

**Task:**
Identify and investigate an unauthorized or suspicious service running on the `target` host that communicates with an external command-and-control (C2) server.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services. Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.

**Hint:**
Check the running services and look for any that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---

**TRAINING_LEVEL 2:**

**Task:**
Determine which network port is used for the suspicious communication identified in the previous task.

**Learning Objective:**
Inspect the C2 service definitions and pay particular attention to `ExecStart`, which specifies the command launched by the service with a port number as an argument.

**Hint:**
Examine the service configuration for the suspicious service to find the port number.

**Validation:**
The hidden flag is the C2 port number.

---

**TRAINING_LEVEL 3:**

**Task:**
Identify and investigate an unauthorized or suspicious service running on the `target` host that runs at boot and every hour thereafter for information collection.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services. Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.

**Hint:**
Check the running services and look for any that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---