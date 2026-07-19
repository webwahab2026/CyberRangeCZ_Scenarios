# BRICKSTORM Backdoor Investigation

## INFO_LEVEL
The target system has exhibited unusual network activity. Your task is to investigate and determine the nature of this activity. The system is running a Linux-based operating system and has shown signs of potential compromise.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is named `target` and is part of the `192.168.50.0/24` network.

## TRAINING_LEVEL 1
**Task:** Investigate the network connections on the target system and identify any suspicious or unauthorized services.

**Question:** What is the name of the suspicious service running on the target system?

**Hint:** Check the list of running services and look for any that are not part of the standard system configuration.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after a system reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd services and timers to identify how the service is scheduled to run.

## TRAINING_LEVEL 3
**Task:** Identify the remote IP address contacted by the suspicious process.

**Question:** What is the IP address used for command-and-control communication?

**Hint:** Analyze the network connections and look for any outbound connections to external addresses.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and analyzing the BRICKSTORM backdoor on the target system. The scenario focuses on discovering the suspicious service, its persistence mechanism, and its command-and-control communication.