# Scenario: Linux/Remaiten.C Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Host: victim (192.168.80.100)
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external server?

**Hint:** Check running services and look for unusual network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating excessive network traffic?

**Hint:** Examine systemd timers and services for unusual activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd timers and services for clues about how the service maintains persistence.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Linux/Remaiten.C botnet activity, with a specific emphasis on identifying and mitigating the botnet's command and control (C2) communication and lateral movement capabilities. The scenario adheres to the sandbox alignment rules and strictly uses only the indicators and infrastructure present in the provided data.