# The Supreme Backdoor Factory Incident Response Scenario

## INFO_LEVEL
The Supreme Backdoor Factory is a collection of malicious GitHub repositories and accounts used to deliver various payloads. The malware involves the use of GitHub for command and control (C2) purposes, with payloads being delivered through malicious repositories. The behavior includes the creation of scheduled tasks to download and execute PowerShell code from dynamic DNS subdomains.

## ACCESS_LEVEL
You have been granted access to the target system as user `cyrano` with password `cyrano`. Your initial entry point is the `target` host at IP address `192.168.50.5`. From this host, you can SSH to other systems in the environment using the same credentials.

## TRAINING_LEVEL 1
**Task:** Investigate the `target` host for any unauthorized or suspicious services running on the system.

**Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Hint:** Check the systemd service manager for any unusual services that might not belong to standard system operations.

**Validation:** The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service identified in the previous task is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:** Examine the systemd service files and timers to understand how the service is scheduled to run.

**Validation:** The hidden flag is the service name or persistence identifier.

## TRAINING_LEVEL 3
**Task:** Investigate the network connections on the `target` host to identify any suspicious communication.

**Objective:** Analyze network traffic and identify suspicious ports or connections.

**Hint:** Use network monitoring tools to inspect active connections and listen ports.

**Validation:** The hidden flag is the C2 port number used for suspicious communication.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is structured to guide students through the investigation process while maintaining alignment with the sandbox's reality and the threat intelligence provided.