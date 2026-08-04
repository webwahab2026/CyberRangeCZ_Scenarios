# Scenario: Linux/AirDropBot Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
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

**Hint:** Investigate systemd services and check for unusual network activity.

**Validation:** The answer should match the service name of the flood service.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd timers and services.

**Validation:** The answer should match the persistence mechanism used by the beacon service.