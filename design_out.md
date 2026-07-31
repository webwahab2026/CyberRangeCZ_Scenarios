# Scenario: Linux/Remaiten Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and identify any malicious activity, determine its scope, and recommend containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Host: victim (192.168.80.100)
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is periodically communicating with an external host?

**Hint:** Check running services and their network connections. Look for services that connect to external hosts on non-standard ports.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating abnormal volumes of network traffic?

**Hint:** Investigate network connections and look for services sending multiple requests to the same destination.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the systemd service responsible for the persistence of the suspicious service?

**Hint:** Check systemd timers and services that might be related to the suspicious service identified in previous tasks.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and containing the Linux/Remaiten botnet activity within the given sandbox environment.