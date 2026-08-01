# CrossRAT Investigation Scenario

## INFO_LEVEL
The target network has been compromised by CrossRAT malware. Your task is to investigate and respond to this incident. CrossRAT is a backdoor tool capable of remote access and control, data exfiltration, and maintaining persistence on infected systems. It targets multiple platforms including Windows, OSX, and Linux.

## ACCESS_LEVEL
You have SSH access to the target system with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target system for suspicious services or processes.

**Question:** What is the name of the suspicious service running on port 2223?

**Hint:** Check running services and network connections.

**Validation:** The answer should match the service name associated with the suspicious activity.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the system.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd services and timers.

**Validation:** The answer should identify the persistence mechanism, such as a specific systemd service or timer.

## TRAINING_LEVEL 3
**Task:** Investigate the file transfers between the target and next-target systems.

**Question:** What is the name of the script responsible for transferring files from the target to next-target?

**Hint:** Look for scripts in the /usr/local/bin directory and examine systemd services.

**Validation:** The answer should match the name of the script used for file transfers.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks focus on investigating and responding to the CrossRAT malware compromise, with a defense-oriented approach suitable for an intermediate difficulty level.