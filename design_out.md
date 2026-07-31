# Sandworm Exaramel Incident Response Scenario

## INFO_LEVEL
The target network has been compromised by the Sandworm threat group using the Exaramel backdoor malware. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and identify lateral movement to other hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes that may indicate malware activity.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd services and timers for any unusual configurations.

## TRAINING_LEVEL 3
**Task:** Investigate the lateral movement from the target host to another host in the network.

**Question:** What is the name of the service responsible for transferring data from the target host to another host?

**Hint:** Look for services that involve file transfers or remote execution.

## Validation
The scenario will be validated based on the correct identification of the suspicious service, its persistence mechanism, and the lateral movement service. The answers should be derived from investigating the target host and its configurations.