# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers that might be responsible for starting the suspicious service.

## TRAINING_LEVEL 3
**Task:** Identify the file or executable associated with the suspicious service.

**Question:** What is the path to the file or executable associated with the suspicious service?

**Hint:** Look for unusual files in the system directories or user home directories that might be related to the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Sofacy Fysbis backdoor, which is a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. The scenario requires students to identify suspicious services, determine persistence mechanisms, and locate associated files or executables. The tasks are structured to guide students through the investigation process while maintaining alignment with the sandbox environment.