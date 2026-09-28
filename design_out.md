# Scenario: Mirai Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external host?

**Hint:** Check the systemd services and look for any unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service that is generating the abnormal network traffic?

**Hint:** Examine the systemd services and look for any services that might be related to network diagnostics or probes.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the timer unit that ensures the suspicious service is automatically started after reboot?

**Hint:** Look for systemd timer units that are associated with the suspicious service identified in the previous tasks.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and mitigating the Mirai botnet activity, specifically the Linux/Mirai-Hilix variant, which targets IoT devices and performs DDoS attacks. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the strict constraints provided.