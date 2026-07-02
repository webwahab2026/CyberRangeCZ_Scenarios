### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a sophisticated Linux rootkit designed to hide its presence and manipulate system processes. It targets both Intel and ARM processors and can perform various malicious activities such as process hiding, network traffic manipulation, and system persistence. The rootkit has been detected in your network, and your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify/investigate/detect suspicious shared library injection
**Description:** Investigate the victim host for any suspicious shared library injections. Look for any unusual libraries that might be loaded system-wide.
**Hint:** Check the `/lib/x86_64-linux-gnu/` directory for any suspicious libraries.
**Flag:** Shared Library Identifier

**TRAINING_LEVEL 2:**
**Task:** Identify/investigate/detect malicious system-wide preload configuration
**Description:** Examine the system-wide preload configuration to identify any malicious entries. This configuration can be found in `/etc/ld.so.preload`.
**Hint:** Look for any unusual paths in the `/etc/ld.so.preload` file.
**Flag:** Preload Configuration Identifier

**TRAINING_LEVEL 3:**
**Task:** Identify/investigate/detect hidden file or directory artifacts
**Description:** Search for any hidden files or directories that might be related to the Umbreon rootkit. These artifacts could be hidden in various locations on the system.
**Hint:** Use commands like `ls -la` to reveal hidden files and directories.
**Flag:** Hidden Artifact Identifier

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and investigating the Umbreon rootkit on the victim host. Each task is mapped to a specific aspect of the rootkit's behavior and is consistent with the sandbox environment.