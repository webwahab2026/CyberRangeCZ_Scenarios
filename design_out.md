# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a Linux rootkit designed to hide its presence and manipulate system processes. It uses various techniques to evade detection and can be used to facilitate other malicious activities. This scenario focuses on investigating and analyzing the Umbreon rootkit on compromised Linux systems.

## ACCESS_LEVEL
You are provided with SSH access to the victim host as the user `cyrano` with the password `cyrano`. From there, you can investigate the system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.

**Description:**
Investigate the victim host for signs of unauthorized shared library injection. Look for indicators that malicious code has been loaded into system processes.

**Hint:**
Check the loaded libraries for each process and look for any unusual or unauthorized libraries.

**Validation:**
The hidden flag is the name of the shared library used for injection.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.

**Description:**
Examine the system-wide preload configuration to see if it has been tampered with. Look for any unauthorized libraries that have been added to the preload list.

**Hint:**
Check the contents of the preload configuration file and look for any suspicious entries.

**Validation:**
The hidden flag is the path to the preload configuration file.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.

**Description:**
Search the victim host for any hidden files or directories that are not visible through standard system utilities. These could be used to store malicious artifacts or configuration data.

**Hint:**
Use alternative methods to list files and directories, as standard utilities may be compromised.

**Validation:**
The hidden flag is the path to a concealed file or directory.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. All tasks are feasible within the given sandbox environment and rely on realistic file paths, logs, configs, modifications, users, credentials, and artifacts derived from the topology and Ansible data. The scenario encourages students to discover the required information through investigation and apply forensic techniques to identify hidden artifacts and malicious activity.