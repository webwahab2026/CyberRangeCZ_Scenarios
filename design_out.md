# XorDDoS Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected outbound network connections and suspicious scheduled tasks. Your task is to investigate and respond to this potential security incident involving the XorDDoS Trojan.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services that may indicate malware activity.

**Hint:** Check running services and their associated processes to identify any anomalies.

**Validation:** The service name associated with the suspicious activity.

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing potentially malicious code on the victim host.

**Hint:** Examine the systemd timers and services to find any unusual scheduled tasks.

**Validation:** The name of the timer or task responsible for the scheduled execution.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the compromised host to understand the extent of the infection.

**Hint:** Search for hidden or unusual directories and files that may contain malware components.

**Validation:** The filename of a key component installed by the malware.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise for incident response training.