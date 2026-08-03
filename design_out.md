# Scenario: Mirai Worm Investigation

## INFO_LEVEL
The network has experienced unusual activity, with multiple systems exhibiting suspicious behavior. Your task is to investigate and contain the threat.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- patient-zero (192.168.90.5)
- host-a (192.168.90.10)
- host-b (192.168.90.20)
- attacker (192.168.90.30)

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on patient-zero that is consuming excessive network resources.

**Hint:** Check the running services and look for any unusual or unauthorized processes.

**Question:** What is the name of the suspicious service?

## TRAINING_LEVEL 2
**Task:** Determine if there is a scheduled task or timer responsible for automatically executing the worm on patient-zero.

**Hint:** Investigate the systemd timers and services to find any suspicious scheduled tasks.

**Question:** What is the name of the timer or task responsible for the worm's persistence?

## TRAINING_LEVEL 3
**Task:** Locate the files installed by the worm on patient-zero.

**Hint:** Search for unusual directories and files, especially those in non-standard locations.

**Question:** What is the name of the directory used to conceal worm components?

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Mirai worm infection, focusing on discovering the required information through systematic analysis of the compromised hosts.