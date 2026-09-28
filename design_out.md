# Scenario: Mirai Worm Investigation

## INFO_LEVEL
The network has experienced unusual activity, with multiple systems exhibiting signs of compromise. Your task is to investigate and contain the threat.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- patient-zero (192.168.90.5)
- host-a (192.168.90.10)
- host-b (192.168.90.20)
- attacker (192.168.90.30)

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on patient-zero that appears to be communicating with an external host.

**Question:** What is the name of the suspicious service?

**Hint:** Check the running services and look for any unusual or unauthorized services.

## TRAINING_LEVEL 2
**Task:** Determine the mechanism used by the worm to automatically execute on the compromised hosts.

**Question:** What is the name of the scheduled task or timer responsible for the automatic execution of the worm?

**Hint:** Investigate the systemd services and timers on the compromised hosts.

## TRAINING_LEVEL 3
**Task:** Identify the directory used by the worm to conceal its components and propagation artifacts.

**Question:** What is the name of the hidden directory used by the worm?

**Hint:** Search for unusual or hidden directories that contain worm-related files.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Mirai worm compromise, focusing on discovering the required information through systematic analysis of the compromised hosts.