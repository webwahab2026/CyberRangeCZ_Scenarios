### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate and respond to this incident. The Fysbis backdoor is a modular Linux trojan that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of Executable and Linking Format (ELF) binaries. Additionally, Fysbis can install itself to a victim system with or without root privileges.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

#### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Question:** What is the name of the suspicious service running on the `target` host?
**Hint:** Check the running services and look for any that seem unusual or unauthorized.
**Flag:** systemkernelservicedefender

#### TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.
**Question:** What is the persistence mechanism used by the suspicious service?
**Hint:** Investigate systemd services and timers to find how the service is started automatically.
**Flag:** lab-checkin.timer

#### TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.
**Question:** What is the service name or filename associated with lateral movement from the `target` host to the `next-target` host?
**Hint:** Check for any services or scripts that transfer files between hosts.
**Flag:** payload-transfer.service

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and uses only the services, hosts, and artifacts that exist within it. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and guidelines provided.