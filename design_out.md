# XorDDoS Botnet Investigation

## INFO_LEVEL
The victim organization has reported unusual network activity and degraded service performance. Your team has been called in to investigate potential cybersecurity incidents. The network consists of several Linux servers, including a command-and-control server, two compromised hosts (bot1 and bot2), and a victim server.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Host: bot1
- Username: cyrano
- Password: cyrano

From this entry point, you can investigate the system and network activity to identify and mitigate any malicious behavior.

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Objective:** Enumerate running services and identify beaconing behavior associated with botnet activity.

**Hint:** Check running services and look for unusual network connections or periodic activity.

**Validation:** The service name must be identified and match the expected malicious service.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Objective:** Distinguish malicious traffic generation services from legitimate network services.

**Hint:** Examine network connections and look for services sending large amounts of data to unexpected destinations.

**Validation:** The service name must be identified and match the expected malicious service.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task, registry).

**Hint:** Investigate system startup configurations and look for entries related to the suspicious service.

**Validation:** The persistence mechanism must be identified and match the expected configuration.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and mitigating the XorDDoS botnet activity within the given sandbox environment.