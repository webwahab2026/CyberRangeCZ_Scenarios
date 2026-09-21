# Adwind/jRAT Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious process activity. Your task is to investigate and respond to this potential security incident involving the Adwind/jRAT trojan.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services that may indicate trojan activity.

**Hint:** Check running services and look for anything unusual or unexpected.

**Validation:** The service name is stored in the flag "service_name".

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing the malware on the victim host.

**Hint:** Investigate systemd timers and services that might be related to the suspicious activity.

**Validation:** The timer or task name is stored in the flag "timer_name".

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the victim host that may provide further evidence of the compromise.

**Hint:** Search for unusual or hidden files that might have been created or modified by the trojan.

**Validation:** The filename is stored in the flag "filename".

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise within the KYPO/CyberRangeCZ environment.