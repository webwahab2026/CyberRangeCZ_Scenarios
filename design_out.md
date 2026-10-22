# Adwind/jRAT Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious process activity. Your task is to investigate and respond to this potential security incident involving the Adwind/jRAT trojan.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services that may indicate trojan activity.

**Objective:** Enumerate running services and identify any that appear unauthorized or suspicious.

**Hint:** Check both active services and systemd timers that might be responsible for scheduled execution.

## TRAINING_LEVEL 2
**Task:** Analyze the victim host for evidence of credential harvesting activity.

**Objective:** Identify any components or scripts responsible for collecting authentication credentials.

**Hint:** Investigate unusual files in the user's home directory and system directories.

## TRAINING_LEVEL 3
**Task:** Determine the command-and-control infrastructure communicating with the compromised host.

**Objective:** Identify the external host and ports used for command-and-control communication.

**Hint:** Examine network connections and logs for unusual outbound traffic patterns.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. All tasks are based on the realistic artifacts and services present in the sandbox environment. The scenario encourages students to discover indicators through thorough investigation rather than being told where to look.