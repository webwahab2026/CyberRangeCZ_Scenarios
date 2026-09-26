# Scenario: Mirai Worm Investigation

## INFO_LEVEL
The network has experienced unusual activity, with multiple systems exhibiting signs of compromise. Your task is to investigate the incident, identify the affected systems, and determine the scope of the compromise.

## ACCESS_LEVEL
You have SSH access to the following systems:
- **patient-zero** (IP: 192.168.90.5)
- **host-a** (IP: 192.168.90.10)
- **host-b** (IP: 192.168.90.20)
- **attacker** (IP: 192.168.90.30)

Use the following credentials to access these systems:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the compromised host.

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

**Question:** What is the name of the suspicious service running on the compromised host?

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing the worm.

**Hint:** Investigate the systemd timers and services to find any that might be related to the suspicious activity.

**Question:** What is the name of the timer or task responsible for the automatic execution of the worm?

## TRAINING_LEVEL 3
**Task:** Locate files installed by the worm on the compromised host.

**Hint:** Search for files in unusual or hidden directories that might be related to the worm's activity.

**Question:** What is the name of the file installed by the worm on the compromised host?

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Mirai worm compromise, focusing on identifying suspicious services, scheduled tasks, and files. The scenario emphasizes multi-host investigation and correlation of evidence across different systems.