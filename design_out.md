# WHIRLPOOL Malware Investigation

## INFO_LEVEL
The Barracuda Email Security Gateway (ESG) device in your network has been compromised by the WHIRLPOOL malware, a Linux ELF reverse shell variant. Your task is to investigate and respond to this security incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on port 4444?

**Hint:** Check running services and network connections.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the name of the systemd service unit file responsible for the persistence of the suspicious service?

**Hint:** Examine systemd service files and timers.

## TRAINING_LEVEL 3
**Task:** Investigate the file associated with the suspicious service.

**Question:** What is the name of the file that the suspicious service is using for its malicious activities?

**Hint:** Look for unusual files in the home directory of the user cyrano.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. All tasks are based on the realistic sandbox environment and the WHIRLPOOL malware indicators.