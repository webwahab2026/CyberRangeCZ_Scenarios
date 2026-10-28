# Rhombus Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external server?

**Hint:** Check the running services and look for any unusual or unauthorized services that might be communicating externally.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating the abnormal network traffic?

**Hint:** Investigate the network connections and look for any services that are sending a high volume of traffic to an unexpected destination.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Check the systemd services and timers to see how the suspicious service is being started automatically.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Rhombus botnet infection, focusing on identifying suspicious services, understanding their behavior, and determining their persistence mechanisms. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the strict constraints provided.