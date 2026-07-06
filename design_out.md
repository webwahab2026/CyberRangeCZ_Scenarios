### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in your organization's network. Kobalos is a complex, multiplatform malware that targets high-performance computing (HPC) clusters and other high-profile systems. It grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify suspicious services and files related to Kobalos malware.
- Investigate lateral movement and data exfiltration activities.
- Contain and mitigate the threat.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with incident response procedures.

**Scenario Duration:** 2 hours

---

#### ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Hosts:**
- next-target (IP: 192.168.50.6)
- c2-server (IP: 192.168.40.5)

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
Investigate the target host for any suspicious services that might be related to the Kobalos malware. Focus on services that are not part of the standard system configuration.

**Steps:**
1. Log in to the target host using SSH.
2. List all running services using the `systemctl list-units --type=service` command.
3. Identify any suspicious services that might be related to Kobalos malware.

**Flag:** service name

**Hint:**
- Look for services that are not part of the standard system configuration.
- Pay attention to services that have been recently added or modified.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Lateral Movement

**Description:**
Investigate the target host for any signs of lateral movement to the next-target host. Focus on any services or processes that might be transferring data between the hosts.

**Steps:**
1. Log in to the target host using SSH.
2. Check the system logs for any signs of data transfer between the target and next-target hosts.
3. Identify any services or processes that might be responsible for the lateral movement.

**Flag:** service name

**Hint:**
- Look for services that are transferring data between the target and next-target hosts.
- Pay attention to any services that have been recently added or modified.

---

#### TRAINING_LEVEL 3
**Task:** Contain C2 Communication

**Description:**
Identify and contain any C2 communication between the target host and the c2-server. Focus on blocking the communication to prevent further data exfiltration.

**Steps:**
1. Log in to the target host using SSH.
2. Identify any outbound connections to the c2-server.
3. Block the communication to prevent further data exfiltration.

**Flag:** Port number

**Hint:**
- Look for any outbound connections to the c2-server.
- Pay attention to any services that are communicating with the c2-server.

---

### Conclusion
By completing these tasks, you will have identified and mitigated the Kobalos malware threat in your organization's network. This scenario provides hands-on experience in incident response and malware investigation.