### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target system has exhibited unusual network activity. Your task is to investigate and identify any malicious activity related to the Sofacy group's Fysbis backdoor. The Fysbis backdoor is known to target Linux systems and can install itself with or without root privileges. It uses a rolling double-XOR algorithm to construct malware installation paths, filenames, and descriptions for a Linux root account.

**ACCESS_LEVEL:**
- Entry Host: `target` (IP: 192.168.50.5)
- Username: `cyrano`
- Password: `cyrano`

---

**TRAINING_LEVEL 1: Suspicious Service Discovery**

**Task:**
Investigate the `target` host and identify any unauthorized or suspicious services running that might be communicating with an external command-and-control (C2) server.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services. Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.

**Hint:**
Check the list of running services and look for any that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---

**TRAINING_LEVEL 2: C2 Communication Discovery (Port)**

**Task:**
Determine which network port is used for the suspicious communication identified in the previous task.

**Learning Objective:**
Inspect the C2 service definitions and pay particular attention to `ExecStart`, which specifies the command launched by the service with a port number as an argument.

**Hint:**
Examine the service configuration file for the suspicious service to find the port number.

**Validation:**
The hidden flag is the C2 port number.

---

**TRAINING_LEVEL 3: Suspicious Data Collection Service Discovery**

**Task:**
Identify and investigate an unauthorized or suspicious service running on the `target` host that runs at boot and every hour thereafter for information collection.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services. Look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.

**Hint:**
Check the list of running services and look for any that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---

**TRAINING_LEVEL 4: Persistence Discovery**

**Task:**
Determine how the suspicious service identified in the previous task is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., the timer) associated with the suspicious service.

**Hint:**
Look for timers or other mechanisms that ensure the service starts automatically.

**Validation:**
The hidden flag is the timer name.

---

**TRAINING_LEVEL 5: Suspicious File Discovery**

**Task:**
Locate the executable or file associated with the suspicious activity identified in the previous tasks.

**Learning Objective:**
Correlate processes with files on disk and identify malicious artifacts.

**Hint:**
Search for files related to the suspicious service and examine their contents.

**Validation:**
The hidden flag is the filename.

---

**TRAINING_LEVEL 6: Data Exfiltration Detection**

**Task:**
Detect evidence of sensitive data being transferred outside the environment.

**Learning Objective:**
Analyze logs, network traffic, and transferred files to identify exfiltration.

**Hint:**
Check network logs and transferred files for any unusual activity.

**Validation:**
The hidden flag is the filename or file hash.

---

**TRAINING_LEVEL 7: Lateral Movement Investigation**

**Task:**
Identify file transfers or remote execution used to move between hosts.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Hint:**
Examine logs and configurations for any evidence of lateral movement.

**Validation:**
The hidden flag is the service name or script.

---

**TRAINING_LEVEL 8: Evidence Collection**

**Task:**
Collect forensic evidence supporting the identified malicious activity.

**Learning Objective:**
Gather relevant logs, process information, service configuration, and network evidence.

**Hint:**
Use appropriate tools to collect and preserve evidence.

**Validation:**
The hidden flag is the script.

---

**TRAINING_LEVEL 9: C2 Containment**

**Task:**
Block communication between the compromised host and the external command-and-control server.

**Learning Objective:**
Apply network controls or firewall rules to contain the threat.

**Hint:**
Use firewall rules or network controls to block the identified C2 communication.

**Validation:**
The hidden flag is the blocked IP address or blocked port.

---

**TRAINING_LEVEL 10: Process Termination**

**Task:**
Stop the malicious process while minimizing impact on legitimate services.

**Learning Objective:**
Safely terminate malicious processes.

**Hint:**
Use appropriate commands to stop the malicious process.

**Validation:**
The hidden flag is the process name or service name.

---

**TRAINING_LEVEL 11: Persistence Removal**

**Task:**
Remove the persistence mechanism used by the malicious service.

**Learning Objective:**
Eliminate persistence to prevent reinfection after reboot.

**Hint:**
Disable or remove the persistence mechanism identified earlier.

**Validation:**
The hidden flag is the service name.

---

**TRAINING_LEVEL 12: Malicious Artifact Removal**

**Task:**
Remove the malicious executable and associated artifacts from the system.

**Learning Objective:**
Perform eradication while preserving relevant evidence.

**Hint:**
Delete the malicious files and ensure they are not present on the system.

**Validation:**
The hidden flag is the filename.

---

**TRAINING_LEVEL 13: Recovery Verification**

**Task:**
Verify that the threat has been successfully removed and no malicious communication remains.

**Learning Objective:**
Validate the effectiveness of containment and eradication actions.

**Hint:**
Check for any remaining signs of malicious activity and ensure all threats are mitigated.

**Validation:**
The hidden flag is the verification checklist or absence of expected indicators.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.