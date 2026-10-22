Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've designed a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Umbreon Rootkit Investigation**

**INFO_LEVEL:**
The Umbreon rootkit is a sophisticated Linux rootkit that provides backdoor access to attackers. It targets both Intel and ARM processors and is designed to hide its presence while manipulating system processes and files. Your task is to investigate and respond to an incident involving this rootkit on a compromised network.

**ACCESS_LEVEL:**
- Entry host: victim (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Identify evidence that a shared library has been injected into system processes.
**Description:** Investigate the victim host for signs of unauthorized shared library injection. Look for unusual libraries loaded into system processes that could indicate rootkit activity.
**Hint:** Check the loaded libraries for system processes and look for any suspicious or unfamiliar entries.
**Validation:** The hidden flag is the identifier of the shared library used for injection.

**TRAINING_LEVEL 2:**
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
**Description:** Examine the victim host for any modifications to the system-wide preload configuration. This could indicate an attempt to load unauthorized code during system startup.
**Hint:** Inspect the preload configuration file and look for any unusual or unexpected entries.
**Validation:** The hidden flag is the identifier of the preload configuration.

**TRAINING_LEVEL 3:**
**Task:** Locate files or directories concealed from normal system utilities.
**Description:** Search the victim host for any hidden files or directories that may have been concealed by the rootkit. These could contain valuable information about the rootkit's activities.
**Hint:** Use alternative forensic techniques to uncover hidden artifacts that standard utilities might miss.
**Validation:** The hidden flag is the identifier of the hidden artifact.

---

This scenario is designed to be consistent with the provided sandbox environment, using only the hosts, services, and artifacts that exist within the topology and Ansible configuration. The tasks are aligned with the NICE Incident Response profile and focus on investigating and responding to the Umbreon rootkit compromise. The scenario encourages students to discover indicators through system, process, service, file system, memory, log, and network analysis, rather than being told where to look. The tasks are technically feasible using the available hosts, services, software, files, and network topology.