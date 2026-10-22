# Scenario: Linux P2P Ransom Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these incidents.

## ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Hostname: victim
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is periodically communicating with an external host?

**Hint:** Check the systemd services and look for any unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating abnormal volumes of network traffic?

**Hint:** Investigate the systemd services and look for any services that might be responsible for network flooding.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd timers and services to understand how the service maintains persistence.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Linux P2P Ransom botnet malware, ensuring that all activities are consistent with the sandbox environment.