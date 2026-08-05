# Scenario: Mirai Worm Investigation

## INFO_LEVEL
The network has experienced unusual activity, with multiple systems exhibiting signs of compromise. Your task is to investigate the incident, identify the affected systems, and determine the scope of the compromise.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- **patient-zero** (192.168.90.5)
- **host-a** (192.168.90.10)
- **host-b** (192.168.90.20)
- **attacker** (192.168.90.30)

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the compromised host **patient-zero**.

**Objective:** Enumerate running services and distinguish legitimate services from worm-related services.

**Hint:** Check the status of all services and look for any that seem unusual or out of place.

**Validation:** The service name must be identified and reported.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing the worm on **host-a**.

**Objective:** Identify scheduled execution persistence mechanisms (e.g., cron, systemd timers, Windows Scheduled Tasks).

**Hint:** Investigate the systemd timers and services to find any that might be related to the worm.

**Validation:** The timer or task name must be identified and reported.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the worm on the compromised host **host-b**.

**Objective:** Correlate suspicious activity with malware artifacts stored on disk.

**Hint:** Search for hidden directories or unusual files that might be related to the worm.

**Validation:** The filename must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and artifacts within the sandbox environment, ensuring a realistic and deployable exercise.