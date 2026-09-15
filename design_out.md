### Scenario: Sofacy Backdoor Investigation

#### INFO_LEVEL
**Scenario Background:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis backdoor is known for its modular architecture and capabilities for command-and-control (C2) communication, exfiltration, and persistence.

**Learning Objectives:**
- Identify and investigate suspicious services and processes.
- Analyze network traffic for signs of C2 communication.
- Investigate lateral movement techniques.
- Collect and analyze forensic evidence.

#### ACCESS_LEVEL
**Entry Host:**
- **Hostname:** target
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**Network Topology:**
- **target (192.168.50.5):** Entry point for investigation.
- **next-target (192.168.50.6):** Potential lateral movement target.
- **c2-server (192.168.40.5):** Suspected command-and-control server.

#### TRAINING_LEVEL 1
**Task: Suspicious Service Discovery**
**Description:**
While monitoring the network, you noticed unusual outbound connections from the `target` host. Your task is to identify and investigate any unauthorized or suspicious services running on this host.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.

**Validation:**
The hidden flag is the name of the suspicious service.

#### TRAINING_LEVEL 2
**Task: C2 Communication Discovery (Port)**
**Description:**
You have identified a suspicious service on the `target` host. Your next step is to determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Use network monitoring tools to inspect active connections and identify the port used by the suspicious service.

**Validation:**
The hidden flag is the C2 port number.

#### TRAINING_LEVEL 3
**Task: Lateral Movement Investigation**
**Description:**
You suspect that the attacker may have moved laterally from the `target` host to the `next-target` host. Your task is to identify any file transfers or remote execution used to move between these hosts.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Hint:**
Check logs and system configurations for evidence of file transfers or remote execution.

**Validation:**
The hidden flag is the service name, filename, or destination host involved in the lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.