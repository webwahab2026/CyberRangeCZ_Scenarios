# Scenario: Remaiten Botnet Investigation

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

**Question:** What is the name of the service generating the flood of network traffic?

**Hint:** Investigate systemd services and look for unusual network activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the timer unit responsible for the persistence of the suspicious service?

**Hint:** Examine systemd timers and look for services that start automatically.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to the Remaiten botnet activity, ensuring that students discover the required information through investigation rather than being given explicit details.