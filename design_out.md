# Mirai Botnet Investigation Scenario

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Hint:** Check running services and their network connections.

**Validation:** The service name must be identified and match the expected beacon service.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Hint:** Examine network connections and service logs for unusual activity.

**Validation:** The service name must be identified and match the expected flood service.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Hint:** Investigate system startup configurations and scheduled tasks.

**Validation:** The persistence mechanism must be identified and match the expected systemd timer service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and mitigating Mirai botnet activity while adhering to the constraints and requirements specified.