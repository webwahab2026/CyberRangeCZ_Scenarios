### Scenario: Linux.Bew Backdoor Investigation

**INFO_LEVEL:**
The network has detected unusual outbound connections from a Linux host. Initial analysis suggests a potential backdoor infection. Your task is to investigate and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target host with the username `cyrano` and password `cyrano`. The target host IP is `192.168.50.5`.

**TRAINING_LEVEL 1:**
**Task:** Investigate Suspicious Outbound Connections
**Description:** The target host has been making unusual outbound connections. Identify the service or process responsible for these connections.
**Hint:** Check the network connections and running services on the target host.
**Validation:** The service name or process responsible for the suspicious connections.

**TRAINING_LEVEL 2:**
**Task:** Determine Persistence Mechanism
**Description:** The suspicious service appears to be persistent across reboots. Identify how it maintains persistence.
**Hint:** Examine systemd services and timers.
**Validation:** The persistence mechanism (e.g., systemd service or timer name).

**TRAINING_LEVEL 3:**
**Task:** Identify Malicious Artifact
**Description:** Locate the executable or file associated with the suspicious service.
**Hint:** Check the service configuration and related files.
**Validation:** The filename or path of the malicious artifact.

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration. Each task is designed to be feasible within the sandbox environment and adheres to the strict constraints provided.