Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario: Kobalos Malware Investigation**

**INFO_LEVEL:**
- The Kobalos malware has been detected in your network. It is a complex backdoor that targets high-performance computing (HPC) clusters and other high-profile systems. Kobalos grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. It also includes a credential stealer component that captures SSH credentials.
- Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry host: `target` (IP: 192.168.50.5)
- Username: `cyrano`
- Password: `cyrano`

**TRAINING_LEVEL 1:**
- **Task:** Identify and investigate the suspicious service that is communicating with the C2 server.
- **Description:** The Kobalos malware is known to create persistent services for communication. Investigate the services running on the `target` host and identify the suspicious one.
- **Hint:** Check the systemd services and look for any unusual or recently created services.
- **Flag:** The name of the suspicious service.

**TRAINING_LEVEL 2:**
- **Task:** Identify the data exfiltration mechanism used by the malware.
- **Description:** Kobalos is known to exfiltrate data from infected systems. Investigate the network connections and file transfers on the `target` host to identify the data exfiltration mechanism.
- **Hint:** Check the logs for any unusual outbound connections or file transfers.
- **Flag:** The filename or service name used for data exfiltration.

**TRAINING_LEVEL 3:**
- **Task:** Contain the C2 communication by blocking the suspicious port.
- **Description:** To prevent further communication with the C2 server, you need to block the port used by the malicious service. Identify the port and implement a containment strategy.
- **Hint:** Use firewall rules or service configuration to block the port.
- **Flag:** The port number used for C2 communication.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks are structured to guide the participants through the investigation and response process, focusing on identifying, investigating, and containing the Kobalos malware. The flags are designed to ensure that the participants engage with the key aspects of the malware's behavior and the sandbox environment.