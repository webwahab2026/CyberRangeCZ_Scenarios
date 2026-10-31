# Scenario: Okiru Worm Investigation

## INFO_LEVEL
The Okiru worm, a variant of the Mirai malware family, has been detected in your network. This worm targets ARC processors based Linux devices and uses exploits to propagate itself. Your task is to investigate the infection, identify the affected hosts, and contain the threat.

## ACCESS_LEVEL
- **Entry Host**: patient-zero (IP: 192.168.90.5)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

## TRAINING_LEVEL 1
**Task**: Identify and investigate an unauthorized or suspicious service running on the compromised host.
**Objective**: Enumerate running services and distinguish legitimate services from worm-related services.
**Hint**: Check the status of all services and look for any that seem unusual or unauthorized.
**Validation**: Service name

## TRAINING_LEVEL 2
**Task**: Determine whether a scheduled task or timer is responsible for automatically executing the worm.
**Objective**: Identify scheduled execution persistence mechanisms.
**Hint**: Investigate the systemd timers and services.
**Validation**: Timer or task name

## TRAINING_LEVEL 3
**Task**: Locate files installed by the worm on the compromised host.
**Objective**: Correlate suspicious activity with malware artifacts stored on disk.
**Hint**: Search for hidden directories and unusual files.
**Validation**: Filename

---

### Notes:
- The scenario is designed to be strictly aligned with the provided sandbox environment and MISP event.
- All tasks are feasible within the given topology and Ansible configuration.
- The tasks encourage multi-host investigation and correlation of evidence across different systems.
- The challenge descriptions focus on observable symptoms rather than revealing hidden implementation details.