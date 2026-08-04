# XorDDoS Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and suspicious scheduled tasks. Your task is to investigate and respond to this potential security incident involving the Linux/XorDDoS malware.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services that may indicate malware activity.

**Hint:** Check running services and their associated processes to identify any anomalies.

**Validation:** The service name associated with the malware's persistence mechanism.

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing the malware on the victim host.

**Hint:** Examine the systemd timers and services to find any suspicious scheduled tasks.

**Validation:** The name of the timer or task responsible for the malware's execution.

## TRAINING_LEVEL 3
**Task:** Identify the component responsible for providing unauthorized remote shell access to the victim host.

**Hint:** Look for scripts or services that establish connections to external hosts on unusual ports.

**Validation:** The script name or service responsible for the reverse shell functionality.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Linux/XorDDoS malware, with a defense-oriented approach suitable for an intermediate difficulty level. The scenario encourages students to discover the required information through investigation rather than being told where to look.