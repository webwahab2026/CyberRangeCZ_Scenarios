### Scenario: XOR.DDoS Malware Investigation

#### INFO_LEVEL
The organization has detected unusual network activity on its Linux servers. Initial analysis suggests the presence of the XOR.DDoS malware family, specifically the Groundhog backdoor. Your task is to investigate and respond to this incident.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised host and any lateral movement to other hosts.

#### TRAINING_LEVEL 1
**Task:** Investigate Suspicious Network Connections
**Description:** While monitoring the `target` host, you notice unusual outbound network connections. Identify the suspicious network port used for this communication.
**Learning Objective:** Analyze network traffic to identify suspicious ports.
**Hint:** Use network monitoring tools to inspect active connections and listen ports.

#### TRAINING_LEVEL 2
**Task:** Identify Lateral Movement Mechanism
**Description:** The attacker appears to be moving laterally within the network. Investigate the `target` host to determine how files are being transferred to the `next-target` host.
**Learning Objective:** Correlate events across hosts to identify attacker lateral movement.
**Hint:** Check system logs and scheduled tasks for evidence of file transfers.

#### TRAINING_LEVEL 3
**Task:** Collect Forensic Evidence
**Description:** Gather forensic evidence from the `target` host to support your findings of malicious activity. This includes logs, process information, and network evidence.
**Learning Objective:** Collect relevant logs, process information, service configuration, and network evidence.
**Hint:** Use command-line tools to gather and preserve evidence for further analysis.

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and deployable exercise.