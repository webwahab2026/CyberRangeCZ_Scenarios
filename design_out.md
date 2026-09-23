### INFO_LEVEL
**Scenario Title:** Umbreon Rootkit Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux system infected with the Umbreon rootkit. Your goal is to identify and analyze the rootkit's presence, persistence mechanisms, and any command-and-control (C2) communication. The rootkit is designed to hide its presence and provide backdoor access to the attacker.

**Learning Objectives:**
- Investigate loaded libraries and detect unauthorized code injection.
- Identify preload-based persistence and code injection mechanisms.
- Apply forensic techniques to identify hidden filesystem artifacts.
- Correlate suspicious activity with malware components stored on disk.
- Detect command-and-control beaconing through log and network analysis.

### ACCESS_LEVEL
**Entry Host:** victim
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH
**Privilege Boundaries:** User-level access with sudo privileges

### TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:**
The Umbreon rootkit is known to inject a shared library into system processes to hide its presence. Investigate the system to identify any evidence of unauthorized shared library injection.
**Hint:**
Check the loaded libraries for system processes and look for any unusual or unauthorized libraries.
**Validation:**
The task is considered successful if the student identifies the shared library injected by the rootkit.

### TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:**
The Umbreon rootkit may modify the system-wide preload configuration to execute unauthorized code. Investigate the system to determine if any modifications have been made to the preload configuration.
**Hint:**
Check the preload configuration file for any unusual or unauthorized entries.
**Validation:**
The task is considered successful if the student identifies the preload configuration modification.

### TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.
**Description:**
The Umbreon rootkit may create hidden files or directories to conceal its presence. Investigate the system to locate any hidden files or directories.
**Hint:**
Use alternative forensic techniques to identify hidden files or directories that are not visible through standard system utilities.
**Validation:**
The task is considered successful if the student identifies the hidden files or directories created by the rootkit.