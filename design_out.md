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

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check running services and look for any unusual or unauthorized services that might be communicating externally.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service responsible for generating abnormal volumes of network traffic?

**Hint:** Investigate network connections and look for services that are generating excessive traffic.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Check systemd timers and services to identify how the service is automatically started.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Linux P2P Ransom botnet, focusing on identifying and mitigating the botnet activity. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the strict constraints provided.