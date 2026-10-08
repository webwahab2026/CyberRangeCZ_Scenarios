Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario focused on investigating and responding to a Linux rootkit infection. The scenario is aligned with the Umbreon rootkit described in the MISP event and the sandbox environment defined in the topology and Ansible data.

### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a Pokémon-themed Linux rootkit that targets both x86 and ARM systems. It is designed to hide its presence and manipulate system processes, making it difficult to detect and remove. The rootkit uses various techniques to maintain persistence and evade detection. Your task is to investigate and respond to this rootkit infection on the victim host.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host's IP address is `192.168.50.5`. You can also access the victim2 host with the same credentials and IP address `192.168.50.6`.

**TRAINING_LEVEL 1:**
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host to find evidence of unauthorized shared library injection. Look for indicators that a malicious library is being loaded into system processes.
**Hint:** Check the loaded libraries for each process and look for any suspicious or unauthorized libraries.
**Q/A:**
Q: What is the name of the unauthorized shared library that has been injected into system processes?
A: libsysmon.so.1

**TRAINING_LEVEL 2:**
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the victim host for any modifications to the system-wide preload configuration that could allow unauthorized code to be executed.
**Hint:** Check the contents of the `/etc/ld.so.preload` file for any suspicious entries.
**Q/A:**
Q: What is the content of the `/etc/ld.so.preload` file that indicates unauthorized code execution?
A: /lib/x86_64-linux-gnu/libsysmon.so.1

**TRAINING_LEVEL 3:**
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Search the victim host for any hidden files or directories that may have been created or modified by the rootkit.
**Hint:** Look for files or directories with unusual names or permissions that are not typically found on a standard Linux system.
**Q/A:**
Q: What is the name of the hidden directory that contains rootkit configuration files?
A: /etc/.kit_conf

This scenario provides a structured approach to investigating and responding to a Linux rootkit infection, with tasks that align with the MISP event, security profile, and sandbox environment. The tasks are designed to encourage students to discover indicators through system, process, service, file system, memory, log, and network analysis. The scenario also includes hints and Q/A sections to guide students and validate their findings.