# BRICKSTORM Backdoor Investigation

## INFO_LEVEL
The target system has exhibited unusual network behavior, including unexpected outbound connections to unknown destinations. Your task is to investigate and determine the nature of this activity.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the `192.168.50.0/24` network.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network connections on the target system.

**Question:** What service is responsible for the unexpected outbound connections?

**Hint:** Check the systemd services and look for any that are not part of the standard system configuration.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the system.

**Question:** What is the name of the systemd service unit file that ensures the suspicious service starts automatically?

**Hint:** Look for service unit files in the `/etc/systemd/system/` directory that are related to the suspicious service.

## TRAINING_LEVEL 3
**Task:** Identify the executable or file associated with the suspicious activity.

**Question:** What is the path to the executable file used by the suspicious service?

**Hint:** Check the service unit file for the suspicious service to find the path to the executable.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the BRICKSTORM backdoor, which uses advanced techniques to evade detection, including SOCKS proxying, multi-layered web service communication, and varied command execution. The scenario also considers the Incident Response profile, which involves investigating, analyzing, and responding to network cybersecurity incidents. The tasks are structured to guide the investigator through the process of identifying and mitigating the threat.