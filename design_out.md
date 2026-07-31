# Scenario: Linux.Mirai Incident Response

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and elevated CPU usage. Your task is to investigate and respond to this potential security incident involving the Linux.Mirai trojan.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services that may indicate trojan activity.

**Hint:** Check running services and their associated processes for anything unusual or unexpected.

**Validation:** The service name associated with the trojan's persistence mechanism.

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing the malware on the victim host.

**Hint:** Investigate systemd timers and services that may be triggering malicious activity.

**Validation:** The name of the timer or task responsible for the trojan's scheduled execution.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the victim host that may provide further evidence of the compromise.

**Hint:** Search for hidden or unusual directories and files that do not belong to standard system applications.

**Validation:** The filename of a key component used by the trojan for its malicious activities.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to a Linux.Mirai trojan incident, with each task building on the previous one to provide a comprehensive understanding of the compromise. The validation criteria ensure that students must actively investigate the system to discover the required information.