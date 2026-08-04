# KAITEN Botnet Incident Response Scenario

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these incidents.

## ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Host: victim
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check running services and look for unusual network connections.

**Validation:** The answer should match the service name of the beacon service.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating abnormal volumes of network traffic?

**Hint:** Investigate network connections and look for services making excessive outbound requests.

**Validation:** The answer should match the service name of the flood service.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Check systemd timers and services for clues about how the service is started automatically.

**Validation:** The answer should match the name of the persistence mechanism (e.g., systemd timer or service).

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to a KAITEN botnet incident, with a specific emphasis on identifying and mitigating the botnet's activities. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.