# Rhombus Botnet Investigation

## INFO_LEVEL
The Rhombus botnet is a Linux DDoS botnet that targets VPS and IoT devices. It includes persistence mechanisms and acts as a dropper for additional malware payloads. Your task is to investigate and respond to a Rhombus botnet infection on compromised systems within your network.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check running services and look for any unusual or unfamiliar services that might be communicating with external hosts.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service responsible for generating abnormal volumes of network traffic?

**Hint:** Investigate network connections and look for services that are sending a high volume of traffic to external hosts.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Check systemd timers and services to identify how the suspicious service is scheduled to run automatically.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and responding to a Rhombus botnet infection, with a specific emphasis on identifying suspicious services, network traffic, and persistence mechanisms. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.