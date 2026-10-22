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

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check running services and look for unusual network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating abnormal volumes of network traffic?

**Hint:** Examine network connections and look for services making multiple connections to the same destination.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the service or mechanism used for persistence?

**Hint:** Check systemd timers and services for any suspicious entries.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Octopus-Rex botnet activity, with a specific emphasis on identifying suspicious services, understanding their behavior, and determining their persistence mechanisms. The scenario adheres to the sandbox constraints and uses only the indicators and infrastructure explicitly present in the provided data.