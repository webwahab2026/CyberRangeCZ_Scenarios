# Linux.Ngioweb Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these incidents. The network consists of several Linux servers, including a command-and-control (C2) server, compromised bots, and a victim server. Use the provided access credentials to log in to the systems and gather information.

## ACCESS_LEVEL
- **Entry Host**: bot1
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

## TRAINING_LEVEL 1
**Task**: Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.
**Objective**: Enumerate running services and identify beaconing behavior associated with botnet activity.
**Hint**: Check running services and their network connections. Look for services that connect to external hosts periodically.
**Validation**: The service name must be identified and match the expected beacon service.

## TRAINING_LEVEL 2
**Task**: Identify the service responsible for generating abnormal volumes of network traffic.
**Objective**: Distinguish malicious traffic generation services from legitimate network services.
**Hint**: Examine network connections and traffic patterns. Look for services that generate a high volume of traffic to a specific target.
**Validation**: The service name must be identified and match the expected flood service.

## TRAINING_LEVEL 3
**Task**: Determine how the suspicious service is automatically started after reboot.
**Objective**: Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).
**Hint**: Check systemd services and timers. Look for services that are enabled and set to start automatically.
**Validation**: The persistence mechanism must be identified and match the expected systemd service or timer.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Linux.Ngioweb botnet, focusing on identifying and mitigating suspicious services and their persistence mechanisms. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the strict constraints provided.