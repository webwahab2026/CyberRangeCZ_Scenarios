# Rakos Backdoor Investigation

## INFO_LEVEL
The Rakos backdoor is a Linux malware that spreads via brute force attempts at SSH logins. It targets both embedded devices and servers with open SSH ports and weak passwords. The malware creates a botnet by compromising unsecured devices and can update its configuration and upgrade itself.

Your task is to investigate and respond to a potential Rakos infection in the network.

## ACCESS_LEVEL
You have access to the `target` host with the following credentials:
- Username: cyrano
- Password: cyrano

From this host, you can investigate the system and any connected devices.

## TRAINING_LEVEL 1
**Task:** Investigate the `target` host for any unauthorized or suspicious services running on the system.

**Question:** What is the name of the suspicious service running on the `target` host?

**Hint:** Check the systemd services and look for any unusual or unauthorized services.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service identified in the previous task is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd unit files and timers to understand how the service is scheduled to run.

## TRAINING_LEVEL 3
**Task:** Investigate the file transfers between the `target` host and the `next-target` host to identify any lateral movement.

**Question:** What is the name of the service responsible for the file transfers between the `target` host and the `next-target` host?

**Hint:** Check the systemd services and logs related to file transfers on the `target` host.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Rakos backdoor, identifying its persistence mechanisms, and detecting lateral movement within the network. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.