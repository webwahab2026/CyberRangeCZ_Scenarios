# Kinsing Rootkit Investigation

## INFO_LEVEL
The Kinsing rootkit is a sophisticated malware family targeting Linux systems. It exploits vulnerabilities to gain unauthorized access, maintains persistence through various mechanisms, and establishes command-and-control (C2) communication channels. Your task is to investigate a compromised system, identify the rootkit's presence, and determine the extent of the compromise.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host to determine if any unauthorized shared libraries have been loaded into system processes. Look for indicators of code injection that could be associated with the Kinsing rootkit.
**Hint:** Check the loaded libraries for each process and look for any suspicious or unauthorized entries.
**Validation:** The hidden flag is the identifier of the shared library used for injection.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the system-wide preload configuration to see if it has been altered to load unauthorized shared libraries. This could indicate a persistence mechanism used by the Kinsing rootkit.
**Hint:** Inspect the preload configuration file and check for any unusual or unauthorized entries.
**Validation:** The hidden flag is the identifier of the preload configuration used for unauthorized code execution.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Search the victim host for any hidden files or directories that may have been created or modified by the Kinsing rootkit. These artifacts could provide valuable insights into the rootkit's behavior and persistence mechanisms.
**Hint:** Use forensic techniques to uncover hidden filesystem artifacts that are not visible through standard system utilities.
**Validation:** The hidden flag is the identifier of the hidden artifact.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Kinsing rootkit compromise, focusing on shared library injection, system-wide preload configuration, and hidden artifacts. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.