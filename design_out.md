# Scenario: Mirai Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external server?

**Hint:** Check the systemd services and look for any unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service that is generating the flood of network traffic?

**Hint:** Examine the systemd services and look for any services that might be responsible for network flooding.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the timer service that ensures the suspicious service starts automatically after reboot?

**Hint:** Look for timer services in the systemd configuration that might be related to the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Mirai botnet infection, focusing on identifying suspicious services, understanding their behavior, and determining their persistence mechanisms. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and infrastructure present in the provided data.