# XOR.DDoS Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that communicates with an external host?

**Hint:** Check running services and their network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating excessive network traffic?

**Hint:** Examine systemd timers and services related to network activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the systemd timer responsible for starting the suspicious service?

**Hint:** Investigate systemd timers and their associated services.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to a Linux-based botnet malware (Groundhog) that uses XOR encryption for its communication, performs DDoS attacks, and exfiltrates data. The scenario emphasizes identifying suspicious services, understanding their behavior, and determining their persistence mechanisms.