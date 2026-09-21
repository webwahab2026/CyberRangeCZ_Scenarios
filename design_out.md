# Umbreon Linux Rootkit Investigation

## INFO_LEVEL
The Umbreon Linux Rootkit targets Linux systems, including both Intel and ARM processors. It is designed to hide processes, files, and network connections from system administrators and security tools. The rootkit uses various techniques to maintain persistence and evade detection.

## ACCESS_LEVEL
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. From there, you can investigate the system and identify signs of the Umbreon rootkit compromise.

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.

**Description:**
Investigate the victim host for signs of unauthorized shared library injection. Look for indicators that malicious code has been loaded into system processes.

**Hint:**
Check the loaded libraries for system processes and look for any unusual or unauthorized entries.

**Validation:**
The hidden flag for this task is the identifier of the shared library used by the rootkit.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.

**Description:**
Examine the system-wide preload configuration to see if it has been tampered with to load unauthorized code. This could indicate a persistence mechanism used by the rootkit.

**Hint:**
Inspect the preload configuration file and check for any suspicious entries.

**Validation:**
The hidden flag for this task is the identifier of the preload configuration used by the rootkit.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.

**Description:**
Search the victim host for any files or directories that are hidden from normal system utilities. These could be artifacts left by the rootkit to maintain its presence on the system.

**Hint:**
Use forensic techniques to uncover hidden files or directories that are not visible through standard commands.

**Validation:**
The hidden flag for this task is the identifier of the hidden artifact used by the rootkit.