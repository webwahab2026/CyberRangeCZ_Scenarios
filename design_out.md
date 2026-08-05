# Earth Lusca Incident Response Scenario

## INFO_LEVEL
The target network has been compromised by the Earth Lusca malware family, specifically the KTLVdoor backdoor. This malware is known for its sophisticated obfuscation techniques and ability to perform various malicious activities including file manipulation, command execution, and remote port scanning. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any lateral movement that may have occurred.

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring the target system, you noticed unusual outbound network connections. Investigate these connections to identify any suspicious activity.
**Hint:** Check the network connections and look for any unusual destinations or ports.
**Validation:** The task is considered successful if the student identifies the suspicious port used for command-and-control communication.

## TRAINING_LEVEL 2
**Task:** Analyze Persistence Mechanism
**Description:** The suspicious service appears to be persisting across reboots. Determine how this service is being automatically started.
**Hint:** Examine systemd services and timers to find any unusual configurations.
**Validation:** The task is considered successful if the student identifies the systemd service or timer responsible for the persistence of the suspicious service.

## TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** There is evidence that the attacker may have moved laterally to another system. Investigate the target system to find any signs of file transfers or remote execution to other hosts.
**Hint:** Check for any scripts or services that are transferring files to other hosts.
**Validation:** The task is considered successful if the student identifies the service or script responsible for lateral movement, including the destination host and any transferred files.