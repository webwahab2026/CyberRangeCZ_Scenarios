# Adwind/jRAT Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious process activity. Your task is to investigate and respond to this potential compromise.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services.

**Objective:** Enumerate running services and identify any that appear unauthorized or suspicious.

**Hint:** Check both active services and systemd timers that might trigger services.

**Hidden Flag:** Service name

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing suspicious processes.

**Objective:** Identify scheduled execution persistence mechanisms that might be used to maintain malware activity.

**Hint:** Look for timers or tasks that trigger services or scripts at regular intervals.

**Hidden Flag:** Timer or task name

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the compromised host.

**Objective:** Correlate suspicious activity with files introduced by the trojan.

**Hint:** Investigate unusual directories and files, especially those with recent modification times.

**Hidden Flag:** Filename

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks focus on investigating and responding to an Adwind/jRAT compromise, with a defense-oriented approach suitable for an intermediate difficulty level. The scenario encourages students to discover indicators through system, process, service, file system, and network analysis.