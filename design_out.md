### Scenario: TeamTNT Hildegard Backdoor Investigation

#### INFO_LEVEL
The target network has been compromised by the TeamTNT malware family, specifically the Hildegard backdoor. This malware is known to establish command and control (C2) connections using a tmate reverse shell and an Internet Relay Chat (IRC) channel. It also uses process disguise, library injection, and payload encryption to evade detection.

Your task is to investigate the compromised hosts, identify the malicious activity, and contain the threat.

#### ACCESS_LEVEL
- **Entry Host**: target (IP: 192.168.50.5)
- **Credentials**: Username: cyrano, Password: cyrano
- **Access Method**: SSH

#### TRAINING_LEVEL 1
**Task**: Suspicious Service Discovery
**Description**: Users have reported slow performance on the target host. Investigate the host to identify any unauthorized or suspicious services running.
**Learning Objective**: Enumerate running services and distinguish legitimate from suspicious services.
**Hint**: Check running services and look for any that seem out of place or unfamiliar.
**Validation**: Service name (bioset.service)

#### TRAINING_LEVEL 2
**Task**: Persistence Discovery
**Description**: Now that you have identified the suspicious service, determine how it is automatically started after reboot.
**Learning Objective**: Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint**: Investigate systemd services and timers.
**Validation**: Service name or persistence identifier (bioset.service)

#### TRAINING_LEVEL 3
**Task**: C2 Communication Discovery (Port)
**Description**: The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication.
**Learning Objective**: Investigate network traffic and identify suspicious ports.
**Hint**: Check network connections and listen ports.
**Validation**: C2 port number (4444)

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is feasible within the sandbox environment and adheres to the strict constraints outlined.