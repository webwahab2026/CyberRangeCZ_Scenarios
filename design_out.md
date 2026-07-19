### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Overview:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in your organization's Linux-based systems. Kobalos is a sophisticated backdoor malware that targets high-performance computing (HPC) clusters and other high-profile systems. It provides remote access to the file system, terminal sessions, and proxying connections to other infected servers. The malware also includes an SSH credential stealer component.

**Learning Objectives:**
- Understand the behavior and indicators of Kobalos malware.
- Investigate and analyze compromised systems for signs of infection.
- Identify and mitigate persistence mechanisms.
- Contain and block C2 communication.

#### ACCESS_LEVEL
**Access Information:**
- **Entry Host:** target
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH
- **IP Address:** 192.168.50.5

#### TRAINING_LEVEL 1
**Task: Identify Suspicious Service**
**Description:**
Investigate the target system for any suspicious services that might be related to the Kobalos malware. Focus on services that are not part of the standard system configuration.

**Hint:**
Check the systemd service list and look for any unusual or unfamiliar services.

**Flag:**
service name

#### TRAINING_LEVEL 2
**Task: Identify Service Persistence Mechanism**
**Description:**
Determine how the suspicious service identified in the previous task maintains persistence on the system. Look for any systemd timers or other mechanisms that ensure the service restarts automatically.

**Hint:**
Examine the systemd timer configurations and check for any scripts or commands that might be responsible for restarting the service.

**Flag:**
service name

#### TRAINING_LEVEL 3
**Task: Contain C2 Communication**
**Description:**
Identify the C2 communication port used by the malware and block it to prevent further communication with the command and control server.

**Hint:**
Check the network connections and listen ports on the target system to identify the C2 communication port.

**Flag:**
Port number

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the incident responder through the investigation and mitigation of a Kobalos malware infection, focusing on identifying suspicious services, persistence mechanisms, and C2 communication.