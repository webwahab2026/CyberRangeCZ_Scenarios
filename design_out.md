Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a Umbreon Linux rootkit infection.

### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a Pokémon-themed Linux rootkit that targets both x86 and ARM systems. It is designed to hide processes, files, and network connections, making it difficult to detect. The rootkit uses various techniques to maintain persistence and evade detection. Your task is to investigate and respond to a suspected Umbreon rootkit infection on the victim host.

**ACCESS_LEVEL:**
- Entry Host: victim (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Identify evidence that a shared library has been injected into system processes.
**Objective:** Investigate loaded libraries and detect unauthorized code injection.
**Hint:** Check the loaded libraries for all running processes and look for any suspicious or unexpected libraries.
**Validation:** The student should identify the presence of the libsysmon.so.1 library loaded into system processes.

**TRAINING_LEVEL 2:**
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Objective:** Identify preload-based persistence and code injection mechanisms.
**Hint:** Inspect the /etc/ld.so.preload file for any unexpected entries.
**Validation:** The student should identify that the /etc/ld.so.preload file contains an entry for the libsysmon.so.1 library.

**TRAINING_LEVEL 3:**
**Task:** Locate files or directories concealed from normal system utilities.
**Objective:** Apply forensic techniques to identify hidden filesystem artifacts.
**Hint:** Use alternative methods to list files and directories, such as examining inode tables or using debugfs.
**Validation:** The student should identify the presence of hidden files or directories, such as /etc/.kit_conf or /home/cyrano/.kit_credentials.txt.

This scenario is designed to be consistent with the provided sandbox environment and MISP event. The tasks focus on investigating and responding to a Umbreon rootkit infection, with a focus on identifying shared library injection, system-wide preload configuration, and hidden filesystem artifacts. The scenario is aligned with the Incident Response security profile and the intermediate difficulty level.