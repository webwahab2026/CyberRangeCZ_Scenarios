Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**INFO_LEVEL**
- **Scenario Title**: Kobalos Malware Investigation
- **Scenario Description**: Investigate and respond to a Kobalos malware infection in a high-performance computing environment.
- **Objective**: Identify and contain the Kobalos malware, investigate its behavior, and prevent further lateral movement.
- **Prerequisites**: Basic knowledge of Linux systems, network security, and incident response procedures.
- **Estimated Time**: 60 minutes

**ACCESS_LEVEL**
- **Entry Host**: target (IP: 192.168.50.5)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH (Port 22)

---

**TRAINING_LEVEL 1**
- **Task**: Identify suspicious service
- **Description**: Investigate the running services on the target host and identify any suspicious services that might be related to the Kobalos malware.
- **Hint**: Check the status of all services and look for any unusual or unfamiliar services.
- **Flag**: payload-transfer.service

**TRAINING_LEVEL 2**
- **Task**: Investigate service persistence mechanism
- **Description**: Examine the persistence mechanism of the suspicious service identified in the previous task.
- **Hint**: Check the systemd service files and timers related to the service.
- **Flag**: payload-transfer.timer

**TRAINING_LEVEL 3**
- **Task**: Identify suspicious file
- **Description**: Search for suspicious files on the target host that might be related to the Kobalos malware.
- **Hint**: Look for files with unusual names or locations, especially in the home directory of the user cyrano.
- **Flag**: fbf0a76ced2939d1f7ec5f9ea58c5a294207f7fe

**TRAINING_LEVEL 4**
- **Task**: Identify suspicious outbound IP
- **Description**: Analyze network connections and identify any suspicious outbound IP addresses that might be used for command and control (C2) communication.
- **Hint**: Use network monitoring tools to inspect outgoing connections.
- **Flag**: 192.168.40.5

**TRAINING_LEVEL 5**
- **Task**: Identify suspicious outbound port
- **Description**: Determine the port used for suspicious outbound communication identified in the previous task.
- **Hint**: Check the network connections and look for the port number used in the communication.
- **Flag**: 7070

**TRAINING_LEVEL 6**
- **Task**: Identify data exfiltration
- **Description**: Investigate whether any data exfiltration is occurring through the suspicious service or network connections.
- **Hint**: Inspect logs and network traffic for any signs of data being sent to external hosts.
- **Flag**: payload-transfer.log

**TRAINING_LEVEL 7**
- **Task**: Contain C2 communication
- **Description**: Implement measures to contain the C2 communication identified in the previous tasks.
- **Hint**: Use firewall rules or other network security measures to block the suspicious outbound communication.
- **Flag**: 7070

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is mapped to real hosts, services, and artifacts present in the topology and Ansible configuration. The tasks follow the training level examples in style and complexity while adhering to the strict MISP constraints and sandbox alignment rules.