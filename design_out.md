### Scenario: Sednit Xagent Incident Response

#### INFO_LEVEL
The Sednit group, also known as APT29, is a sophisticated cyber espionage group believed to be operating out of Russia. They are known for targeting government agencies, diplomatic organizations, and research institutions. The Sednit group uses a variety of malware, including Xagent, a backdoor malware capable of establishing persistent connections to command and control (C2) servers, executing commands, and exfiltrating data.

In this scenario, you will investigate a compromised network where the Sednit group's Xagent malware has been detected. Your goal is to identify the malware, understand its behavior, and contain the threat.

#### ACCESS_LEVEL
- **Entry Host**: `target` (IP: 192.168.50.5)
- **Username**: `cyrano`
- **Password**: `cyrano`

#### TRAINING_LEVEL 1
**Task**: Suspicious Service Discovery
**Description**: Users have reported slow performance on the `target` host. Investigate and identify any unauthorized or suspicious services running on this host.
**Learning Objective**: Enumerate running services and distinguish legitimate from suspicious services.
**Hint**: Check the list of running services and look for any that seem out of place or unfamiliar.
**Validation**: The service name `bkd.service` should be identified as suspicious.

#### TRAINING_LEVEL 2
**Task**: Persistence Discovery
**Description**: Now that you have identified the suspicious service, determine how it is automatically started after reboot.
**Learning Objective**: Identify persistence mechanisms (e.g., systemd, cron, scheduled task).
**Hint**: Investigate the systemd configuration files to find how the service is set to start automatically.
**Validation**: The persistence mechanism should be identified as a systemd service unit file located at `/etc/systemd/system/bkd.service`.

#### TRAINING_LEVEL 3
**Task**: C2 Communication Discovery (Port)
**Description**: The suspicious service appears to be communicating with an external command and control server. Determine which network port is used for this communication.
**Learning Objective**: Investigate network traffic and identify suspicious ports.
**Hint**: Check the service configuration to see which port it is listening on.
**Validation**: The C2 port number `4444` should be identified as the port used for suspicious communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and file paths within the sandbox environment, ensuring a realistic and deployable exercise.