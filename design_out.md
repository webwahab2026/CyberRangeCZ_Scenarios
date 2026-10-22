# KAITEN Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external server?

**Hint:** Check the running services and look for any unusual or unauthorized network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating the abnormal network traffic?

**Hint:** Examine the systemd services and look for any unusual or high-frequency network activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Investigate the systemd timers and services to find how the suspicious service is scheduled to run periodically.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.