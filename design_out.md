# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a Linux rootkit designed to hide its presence and provide backdoor access to attackers. It targets both Intel and ARM processors and can manipulate system processes and files, making it difficult to detect and remove. This scenario focuses on investigating and analyzing a compromised system infected with the Umbreon rootkit.

## ACCESS_LEVEL
You are provided with SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host for signs of unauthorized shared library injection. Look for indicators that suggest malicious code has been loaded into system processes.
**Hint:** Check the loaded libraries for each process and look for any unusual or unexpected entries.
**Validation:** The hidden flag is the identifier of the shared library used for injection.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the system-wide preload configuration on the victim host. Look for any modifications that could allow unauthorized code to be executed.
**Hint:** Check the contents of the preload configuration file and verify its integrity.
**Validation:** The hidden flag is the identifier of the preload configuration.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Search the victim host for any hidden files or directories that are not visible through standard system utilities. These could be used to store malicious artifacts or configuration data.
**Hint:** Use alternative methods to list files and directories, as standard utilities may be compromised.
**Validation:** The hidden flag is the identifier of the concealed artifact.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a system compromised by the Umbreon rootkit, focusing on discovering shared library injection, system-wide preload modifications, and hidden artifacts. The scenario emphasizes the use of alternative forensic techniques to bypass rootkit concealment mechanisms.