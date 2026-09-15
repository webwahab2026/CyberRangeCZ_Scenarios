### Scenario: Sofacy Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** Sofacy Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis backdoor on a Linux-based network. The Fysbis backdoor is known for its modular capabilities, including command-and-control (C2) communication, lateral movement, and data exfiltration. Your mission is to identify, analyze, and mitigate the threat.

**Learning Objectives:**
1. Identify and investigate suspicious services and processes.
2. Analyze network traffic for signs of C2 communication.
3. Investigate lateral movement techniques.
4. Collect and analyze forensic evidence.
5. Implement containment and eradication measures.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with network protocols and services.
- Understanding of incident response procedures.

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual activity on the `target` host. Your task is to identify and investigate any unauthorized or suspicious services running on this host.

**Steps:**
1. Log in to the `target` host using the provided credentials.
2. Enumerate all running services and processes.
3. Identify any services or processes that appear suspicious or unauthorized.
4. Document the name of the suspicious service.

**Hint:**
- Use commands like `systemctl list-units --type=service`, `ps aux`, and `netstat -tuln` to enumerate services and processes.
- Look for services that are not part of the standard system configuration or have unusual names.

**Validation:**
- The hidden flag is the name of the suspicious service.

#### TRAINING_LEVEL 2
**Task:** C2 Communication Discovery (Port)
**Description:**
You have identified a suspicious service on the `target` host. Your next task is to determine which network port is used for the suspicious communication.

**Steps:**
1. Investigate the network connections associated with the suspicious service.
2. Identify the port used for communication.
3. Document the port number.

**Hint:**
- Use commands like `netstat -tuln`, `ss -tuln`, or `lsof -i` to identify network connections.
- Look for connections to external IPs or unusual ports.

**Validation:**
- The hidden flag is the port number used for C2 communication.

#### TRAINING_LEVEL 3
**Task:** Lateral Movement Investigation
**Description:**
You suspect that the attacker may have moved laterally within the network. Your task is to identify any file transfers or remote execution used to move between hosts.

**Steps:**
1. Investigate the `target` host for any signs of lateral movement.
2. Look for evidence of file transfers or remote execution.
3. Document the service name, filename, or destination host involved in the lateral movement.

**Hint:**
- Check system logs for any unusual file transfers or remote commands.
- Use commands like `grep` to search through logs for relevant information.

**Validation:**
- The hidden flag is the service name, filename, or destination host involved in the lateral movement.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to the sandbox environment and uses only the services, hosts, and artifacts that exist within the sandbox. The tasks are structured to guide students through the investigation process while adhering to the constraints and requirements provided.