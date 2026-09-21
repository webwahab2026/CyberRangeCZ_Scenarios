# Scenario: Linux/Remaiten Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and identify any malicious activity, determine its scope, and recommend containment measures.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that communicates with an external host?

**Hint:** Check running services and look for unusual network connections.

**Validation:** The service name must match the exact name of the beacon service running on the system.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating excessive network traffic?

**Hint:** Examine systemd timers and services for unusual activity.

**Validation:** The service name must match the exact name of the flood service running on the system.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd timers and services for clues about automatic execution.

**Validation:** The persistence mechanism must match the exact name of the systemd timer or service responsible for starting the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and containing the Linux/Remaiten botnet activity while adhering to the constraints and requirements specified.