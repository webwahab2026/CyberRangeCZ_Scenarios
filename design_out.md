### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromise, identify the malicious activity, and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and identify lateral movement to other hosts.

#### TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Activity
**Description:** Users have reported slow network performance. Investigate the `target` host for any suspicious network activity that could be causing this issue.
**Hint:** Check the network connections and running services on the `target` host.
**Validation:** The task is considered successful if the student identifies the suspicious port `80` used for communication.

#### TRAINING_LEVEL 2
**Task:** Identify Persistence Mechanism
**Description:** Determine how the suspicious service is automatically started after reboot on the `target` host.
**Hint:** Look for systemd services or cron jobs that might be responsible for starting the suspicious service.
**Validation:** The task is considered successful if the student identifies the systemd service `ksysdefd.service` responsible for the persistence.

#### TRAINING_LEVEL 3
**Task:** Investigate Lateral Movement
**Description:** Check if the attacker has moved laterally from the `target` host to the `next-target` host.
**Hint:** Look for any scripts or services that might be transferring files or executing commands remotely.
**Validation:** The task is considered successful if the student identifies the script `/usr/local/bin/payload-transfer.sh` used for lateral movement.

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.