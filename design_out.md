# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a Linux rootkit designed to hide its presence and provide backdoor access to attackers. It targets both Intel and ARM processors and is capable of command-and-control communication, lateral movement, data exfiltration, and persistence. This scenario focuses on investigating and containing the Umbreon rootkit on compromised Linux systems.

## ACCESS_LEVEL
You are provided with SSH access to the victim host as the user 'cyrano' with the password 'cyrano'. From this host, you can investigate the compromise and attempt to contain the threat.

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.

**Description:**
Investigate the victim host for signs of unauthorized shared library injection. Look for evidence that malicious code has been loaded into system processes.

**Hint:**
Check the loaded libraries for system processes and look for any unusual or unauthorized libraries.

**Validation:**
The hidden flag for this task is the identifier of the shared library used for injection.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.

**Description:**
Examine the system-wide preload configuration to determine if it has been tampered with to load unauthorized code. This could indicate a persistence mechanism for the rootkit.

**Hint:**
Inspect the preload configuration file and check for any unusual or unauthorized library paths.

**Validation:**
The hidden flag for this task is the identifier of the preload configuration.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.

**Description:**
Search the victim host for any hidden files or directories that may have been created or modified by the rootkit. These artifacts could provide valuable information about the rootkit's behavior and persistence mechanisms.

**Hint:**
Use alternative forensic techniques to uncover hidden artifacts that may not be visible through standard system utilities.

**Validation:**
The hidden flag for this task is the identifier of the hidden artifact.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Umbreon rootkit, focusing on shared library injection, preload configuration modification, and hidden artifact discovery. The scenario emphasizes the use of alternative forensic techniques to bypass rootkit concealment mechanisms.