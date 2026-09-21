# Tsunami/Kaiten Incident Response Scenario

## INFO_LEVEL
The Tsunami/Kaiten malware is a Unix Trojan known as Tsunami/Kaiten.c, which operates as an IRC/Bot with flooder and backdoor capabilities. It exploits web admin panel abuse via HTTP access to gain root privilege through crontab UID manipulation. The malware deletes source traces and logs, runs and hides its service using a fake bash process, and communicates via IRC ports.

Your task is to investigate and respond to this incident on the target system.

## ACCESS_LEVEL
You have SSH access to the target system with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target system for any unauthorized or suspicious services running.

**Question:** What is the name of the suspicious service you identified?

**Hint:** Check the systemd services and look for any unusual or unfamiliar services.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd unit files and timers to understand how the service is scheduled to run.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Question:** What is the path to the executable or file associated with the suspicious service?

**Hint:** Investigate the service unit files and scripts to find the path to the executable or file.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process for the Tsunami/Kaiten malware incident.