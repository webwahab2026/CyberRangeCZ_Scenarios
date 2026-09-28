# TeamTNT Hildegard Incident Response Scenario

## INFO_LEVEL
The target network has been compromised by the TeamTNT malware family, specifically the Hildegard backdoor. This malware is known to establish command and control (C2) connections through tmate reverse shells and Internet Relay Chat (IRC) channels. It disguises itself using legitimate Linux process names and employs library injection techniques.

Your task is to investigate and respond to this incident, following standard incident response procedures to contain and eradicate the threat.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

From this host, you can SSH to other hosts in the network using the same credentials.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Objective:** Identify any unauthorized or suspicious services running on the target host.

**Hint:** Check running services and processes, looking for anything unusual or unexpected.

**Validation:** The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify the persistence mechanism used by the suspicious service.

**Hint:** Investigate systemd services, cron jobs, or other scheduled tasks.

**Validation:** The hidden flag is the name of the service or persistence identifier.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Objective:** Correlate processes with files on disk and identify malicious artifacts.

**Hint:** Search for files related to the suspicious service or process.

**Validation:** The hidden flag is the filename or file path.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. All tasks are feasible within the given topology and Ansible configuration, and only use indicators and artifacts explicitly present in the MISP event or derived from the sandbox.