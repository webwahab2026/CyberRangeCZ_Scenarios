# Octopus-Rex Botnet Investigation

## INFO_LEVEL
The Octopus-Rex botnet is a multi-task botnet capable of various malicious activities including command and control (C2) communication, lateral movement, and data exfiltration. Your task is to investigate and contain this botnet infection on compromised systems within the network.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service responsible for beaconing activity?

**Hint:** Check running services and look for unusual network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating the flood attack traffic?

**Hint:** Investigate systemd timers and services for unusual network activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd timers and services for clues about automatic startup.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging investigation exercise for incident responders.