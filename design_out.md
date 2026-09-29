### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate and respond to this incident. The Fysbis malware is a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of Executable and Linking Format (ELF) binaries. The malware can install itself on a victim system with or without root privileges, providing flexibility for adversaries in selecting accounts for installation. It has capabilities for remote shell access, persistence, and command and control (C2) communication.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

#### TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring the `target` host, you notice unusual outbound network connections. Identify the suspicious network port used for these connections.
**Hint:** Check the network connections and look for any unusual ports.
**Validation:** The correct port number is required to validate the task.

#### TRAINING_LEVEL 2
**Task:** Identify Persistence Mechanism
**Description:** Determine how the suspicious service is automatically started after reboot on the `target` host.
**Hint:** Investigate systemd services and timers.
**Validation:** The correct service name or persistence identifier is required to validate the task.

#### TRAINING_LEVEL 3
**Task:** Collect Forensic Evidence
**Description:** Gather forensic evidence supporting the identified malicious activity on the `target` host. This includes relevant logs, process information, service configuration, and network evidence.
**Hint:** Look for logs in `/var/log/` and check running processes.
**Validation:** The expected evidence set is required to validate the task.

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration. Each task is designed to be feasible within the sandbox environment and focuses on investigating and responding to the Sofacy Fysbis backdoor compromise.