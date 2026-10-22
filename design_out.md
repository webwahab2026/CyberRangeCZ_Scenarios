# CrossRAT Investigation Scenario

## INFO_LEVEL
The target network has been compromised by CrossRAT, a cross-platform surveillanceware tool. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on port 2223?

**Hint:** Check running services and network connections.

**Answer:** bkd.service

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the system.

**Question:** What is the name of the timer unit responsible for the persistence of the suspicious service?

**Hint:** Examine systemd timers and services.

**Answer:** lab-checkin.timer

## TRAINING_LEVEL 3
**Task:** Investigate the lateral movement capabilities of the malware.

**Question:** What is the name of the script used for transferring files to the next-target host?

**Hint:** Check for scripts in the /usr/local/bin directory and examine systemd services.

**Answer:** payload-transfer.sh

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. All tasks are based on the actual services, files, and configurations present in the sandbox. The scenario focuses on investigating and responding to the CrossRAT malware, with tasks that require enumeration, persistence analysis, and lateral movement investigation.