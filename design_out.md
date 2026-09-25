# Fancy Bear Incident Response Scenario

## INFO_LEVEL
Fancy Bear, also known as APT29, is a sophisticated cyber espionage group known for targeting government, military, and corporate networks. This scenario simulates an incident involving Fancy Bear malware on your network. Your task is to investigate, analyze, and respond to this cybersecurity incident.

## ACCESS_LEVEL
You have access to the `target` host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Activity
**Description:** Users have reported slow network performance. Investigate the `target` host to identify any suspicious network activity.
**Hint:** Check running services and network connections.
**Validation:** The task is considered successful if the student identifies the suspicious service running on port 4444.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanism
**Description:** Now that you have identified the suspicious service, determine how it is maintained on the system. Investigate the persistence mechanism used by the service.
**Hint:** Check systemd services and timers.
**Validation:** The task is considered successful if the student identifies the systemd timer responsible for the suspicious service.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** Check if the attacker has moved laterally to other hosts in the network. Investigate any file transfers or remote execution activities from the `target` host.
**Hint:** Check logs and systemd services related to file transfers.
**Validation:** The task is considered successful if the student identifies the service responsible for transferring files to the `next-target` host.