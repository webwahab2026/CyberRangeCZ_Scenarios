# Sandworm Incident Response Exercise

## INFO_LEVEL
The Centreon system at your organization has been compromised by the Sandworm intrusion set, specifically using the P.A.S. webshell backdoor. This malware provides capabilities for file manipulation, network tools, SQL client connections, and password brute-forcing. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system is at IP address `192.168.50.5`.

## TRAINING_LEVEL 1
**Task:** Investigate the target system for unauthorized or suspicious services running on the host.

**Question:** What is the name of the suspicious service running on the target system?

**Hint:** Check the systemd services and look for any services that seem out of place or have unusual configurations.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd unit files and timers to identify how the service is set to start automatically.

## TRAINING_LEVEL 3
**Task:** Identify the process responsible for suspicious activity on the host.

**Question:** What is the name of the process responsible for the suspicious activity?

**Hint:** Use process monitoring tools to identify any unusual processes and correlate them with the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.