# Linux/NyaDrop Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious file modifications. Your task is to investigate and respond to this potential security incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services.

**Objective:** Enumerate running services and distinguish legitimate services from malicious ones.

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

**Flag:** [Service name]

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing suspicious activity.

**Objective:** Identify scheduled execution persistence mechanisms.

**Hint:** Investigate the systemd timers and services to find any that might be related to the suspicious activity.

**Flag:** [Timer or task name]

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Objective:** Correlate suspicious activity with newly created files and identify malware artifacts.

**Hint:** Search for recently modified or created files in unusual directories.

**Flag:** [Filename]

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Linux/NyaDrop malware incident, focusing on service discovery, scheduled task investigation, and file artifact identification. The flags are based on the actual sandbox environment and MISP indicators.