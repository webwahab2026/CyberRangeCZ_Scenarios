# Scenario: Mirai Okiru Worm Investigation

## INFO_LEVEL
The network has experienced unusual activity, with multiple systems exhibiting suspicious behavior. Your task is to investigate and contain the threat.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- patient-zero (192.168.90.5)
- host-a (192.168.90.10)
- host-b (192.168.90.20)
- attacker (192.168.90.30)

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on patient-zero that appears to be communicating with an external host.

**Question:** What is the name of the suspicious service?

**Hint:** Check the systemd services and look for any unusual or unauthorized services.

## TRAINING_LEVEL 2
**Task:** Determine the mechanism used by the worm to automatically execute on the compromised hosts.

**Question:** What is the name of the scheduled task or timer responsible for the automatic execution of the worm?

**Hint:** Investigate the systemd timers and look for any unusual or unauthorized timers.

## TRAINING_LEVEL 3
**Task:** Locate the files installed by the worm on the compromised host patient-zero.

**Question:** What is the name of the directory used to conceal worm components or propagation artifacts?

**Hint:** Search for hidden or unusual directories that may contain worm-related files.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the Mirai Okiru worm, focusing on discovering the required information through systematic analysis of the compromised hosts. The scenario emphasizes multi-host investigation and correlation of evidence across different systems.