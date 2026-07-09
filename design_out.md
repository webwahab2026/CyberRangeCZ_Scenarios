### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a Linux rootkit that targets both x86 and ARM systems. It is designed to hide its presence and provide backdoor access to the attacker. The rootkit uses various techniques to maintain persistence and evade detection. Your task is to investigate and analyze the compromised systems to identify and mitigate the rootkit's presence.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious shared library injection.
**Description:** Investigate the system for any suspicious shared libraries that might be injected into the system's library path.
**Hint:** Check the `/lib/x86_64-linux-gnu/` directory for any unusual libraries.
**Flag:** Shared Library Identifier

**TRAINING_LEVEL 2:**
**Task:** Identify the malicious system-wide preload configuration.
**Description:** Examine the system-wide preload configuration to detect any malicious entries that might be used to load suspicious libraries.
**Hint:** Check the `/etc/ld.so.preload` file for any unusual entries.
**Flag:** Preload Configuration Identifier

**TRAINING_LEVEL 3:**
**Task:** Identify the hidden file or directory artifacts.
**Description:** Search for any hidden files or directories that might be used by the rootkit to store configuration files, logs, or other artifacts.
**Hint:** Look for files or directories with names starting with a dot (e.g., `.kit_`).
**Flag:** Hidden Artifact Identifier

---

**Note:** The scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. All tasks and flags are derived from the sandbox's topology, Ansible configuration, and the MISP event's indicators. The tasks focus on investigating and mitigating the Umbreon rootkit's presence on the victim host.