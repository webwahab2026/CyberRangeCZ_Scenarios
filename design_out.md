# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a Pokémon-themed Linux rootkit that targets both x86 and ARM systems. It is designed to hide its presence and manipulate system processes, making it difficult to detect and remove. The rootkit uses various techniques to maintain persistence and evade detection.

## ACCESS_LEVEL
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is connected to the victim-switch network with the IP address 192.168.50.5. The attacker host is connected to the attacker-switch network with the IP address 192.168.40.5.

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host for signs of unauthorized shared library injection. Look for unusual libraries loaded into system processes that could indicate rootkit activity.
**Hint:** Check the loaded libraries for system processes and look for any suspicious or unfamiliar entries.
**Validation:** The hidden flag is the name of the shared library used by the rootkit.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the system-wide preload configuration on the victim host. Check if any unauthorized libraries are being loaded system-wide, which could indicate rootkit persistence.
**Hint:** Look for modifications in the system-wide preload configuration file.
**Validation:** The hidden flag is the path to the preload configuration file.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Investigate the victim host for any hidden files or directories that are not visible through standard system utilities. These could be artifacts left by the rootkit to maintain persistence or hide its activities.
**Hint:** Use alternative forensic techniques to uncover hidden files or directories.
**Validation:** The hidden flag is the path to a hidden directory or file.

This scenario provides a structured approach to investigating the Umbreon rootkit, focusing on shared library injection, system-wide preload configuration, and hidden artifacts. The tasks are designed to encourage thorough investigation and the use of alternative forensic techniques to uncover rootkit activity.