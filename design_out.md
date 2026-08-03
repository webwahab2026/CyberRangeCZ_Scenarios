# TeamTNT Hildegard Incident Response Scenario

## INFO_LEVEL
The target network has been compromised by the TeamTNT malware family, specifically the Hildegard backdoor. This malware is known to establish command and control (C2) connections using tmate reverse shells and Internet Relay Chat (IRC) channels. It disguises itself using legitimate Linux process names and employs library injection techniques.

Your task is to investigate and respond to this incident, following standard incident response procedures to contain and eradicate the threat.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

From this host, you can investigate the compromise and take appropriate response actions.

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Process Activity

**Description:**
While monitoring system logs, you noticed unusual process activity on the target host. Investigate the running processes to identify any suspicious or unauthorized activity.

**Objective:**
Identify the suspicious process associated with the Hildegard malware.

**Hint:**
Look for processes that don't match typical system processes or those with unusual command lines.

**Validation:**
The hidden flag is the name of the suspicious process.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanism

**Description:**
Now that you've identified the suspicious process, determine how it maintains persistence on the system. Investigate the system's startup mechanisms to find how the malicious process is automatically started after reboot.

**Objective:**
Identify the persistence mechanism used by the Hildegard malware.

**Hint:**
Check systemd services, cron jobs, and other common persistence locations.

**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement

**Description:**
With the persistence mechanism identified, investigate whether the malware has attempted to move laterally within the network. Look for evidence of file transfers or remote execution to other hosts.

**Objective:**
Identify any lateral movement activity initiated by the Hildegard malware.

**Hint:**
Check for SSH connections, file transfers, or remote command execution to other hosts in the network.

**Validation:**
The hidden flag is the destination host or service name used for lateral movement.

---

This scenario aligns with the provided MISP event, security profile, and sandbox environment. The tasks are designed to guide students through the incident response process, focusing on identifying and containing the Hildegard malware. The scenario uses only the indicators and artifacts present in the MISP event and the sandbox environment, ensuring strict alignment with the provided data.