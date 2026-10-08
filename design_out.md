### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromise, identify the malicious activity, and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and identify lateral movement to other hosts.

#### TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Description:** The `target` host is exhibiting unusual network activity. Investigate the running services to identify any unauthorized or suspicious services.
**Hint:** Check the systemd services and look for any services that do not belong to standard system services.
**Validation:** The service name `systemkernelservicedefender.service` should be identified as suspicious.

#### TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.
**Description:** The suspicious service identified in the previous task is persisting across reboots. Investigate how this service is being automatically started.
**Hint:** Check the systemd unit files and timers to identify the persistence mechanism.
**Validation:** The persistence mechanism should be identified as a systemd timer `lab-checkin.timer` starting the service `systemkernelservicedefender.service`.

#### TRAINING_LEVEL 3
**Task:** Identify file transfers or remote execution used to move between hosts.
**Description:** The attacker may have moved laterally to other hosts in the network. Investigate the `target` host to identify any evidence of lateral movement.
**Hint:** Check the logs and systemd services for any evidence of file transfers or remote execution.
**Validation:** The service name `payload-transfer.service` should be identified as evidence of lateral movement to the `next-target` host.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the student through the investigation of the Sofacy Fysbis backdoor, focusing on service discovery, persistence mechanisms, and lateral movement. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.