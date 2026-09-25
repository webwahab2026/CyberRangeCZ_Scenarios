### Scenario: TeamTNT Hildegard Backdoor Investigation

#### INFO_LEVEL
The security team has detected unusual network activity originating from the target host in your environment. Initial analysis suggests a potential compromise by the TeamTNT Hildegard backdoor malware, which targets Kubernetes clusters and performs cryptojacking operations. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

#### ACCESS_LEVEL
- **Entry Host**: target (IP: 192.168.50.5)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

#### TRAINING_LEVEL 1
**Task**: Investigate Suspicious Network Connections
**Description**: While monitoring the target host, you notice unusual outbound network connections. Identify the suspicious network port used for this communication.
**Learning Objective**: Analyze network traffic and identify suspicious ports.
**Hint**: Check the system logs for recent network connections.
**Validation**: The correct port number must be provided.

#### TRAINING_LEVEL 2
**Task**: Identify Persistence Mechanism
**Description**: The suspicious service appears to be automatically started after reboot. Determine how this persistence is achieved.
**Learning Objective**: Identify persistence mechanisms such as systemd, cron, or scheduled tasks.
**Hint**: Examine the systemd service files and timers.
**Validation**: The persistence mechanism (e.g., service name or timer) must be correctly identified.

#### TRAINING_LEVEL 3
**Task**: Locate Malicious Artifact
**Description**: Find the executable or file associated with the suspicious activity on the target host.
**Learning Objective**: Correlate processes with files on disk and identify malicious artifacts.
**Hint**: Search for unusual files in the home directory of the user cyrano.
**Validation**: The correct filename or file path must be provided.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise within the KYPO/CyberRangeCZ environment.