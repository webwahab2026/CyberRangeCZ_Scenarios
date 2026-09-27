# Octopus-Rex Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Host: victim
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external server?

**Hint:** Check running services and look for unusual network connections.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd timers and services.

## TRAINING_LEVEL 3
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating the abnormal network traffic?

**Hint:** Analyze network connections and look for services making multiple connections to the same destination.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Octopus-Rex botnet activity, with a specific emphasis on identifying suspicious services, persistence mechanisms, and abnormal network traffic. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.