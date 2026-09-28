Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a Umbreon Linux rootkit infection.

### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a Pokémon-themed Linux rootkit that targets both x86 and ARM systems. It is designed to hide processes, files, and network connections from system administrators and security tools. The rootkit uses various techniques to maintain persistence and evade detection. Your task is to investigate the compromised systems and respond to the incident.

**ACCESS_LEVEL:**
You have SSH access to the victim and victim2 hosts as the user cyrano with the password cyrano. The attacker host is not accessible.

**TRAINING_LEVEL 1:**
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host for signs of unauthorized shared library injection. Look for evidence that a shared library has been loaded into system processes without proper authorization.
**Hint:** Check the loaded libraries for system processes and look for any unusual or unauthorized libraries.
**Validation:** The hidden flag is the name of the shared library that has been injected.

**TRAINING_LEVEL 2:**
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the victim host for modifications to the system-wide preload configuration. Look for any unauthorized entries that could be used to load malicious code at system startup.
**Hint:** Check the preload configuration file for any unusual or unauthorized entries.
**Validation:** The hidden flag is the path to the preload configuration file that has been modified.

**TRAINING_LEVEL 3:**
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Investigate the victim host for hidden files or directories that are not visible through standard system utilities. These could be used to store malicious code or configuration data.
**Hint:** Use alternative forensic techniques to uncover hidden files or directories.
**Validation:** The hidden flag is the path to a hidden file or directory that has been located.

This scenario provides a structured approach to investigating and responding to a Umbreon rootkit infection. The tasks are designed to guide students through the process of identifying and mitigating the rootkit's persistence mechanisms, concealment techniques, and command-and-control communication. The scenario is aligned with the provided MISP event, security profile, and sandbox environment.