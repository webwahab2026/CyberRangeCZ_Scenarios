### Scenario: Kobalos Malware Investigation

#### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection in your organization's network. Kobalos is a complex, multiplatform malware that targets high-performance computing (HPC) clusters and other high-profile systems. It grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. Your goal is to identify and mitigate the malware's presence.

**Learning Objectives:**
- Identify suspicious services and files related to Kobalos malware.
- Investigate lateral movement and data exfiltration activities.
- Contain and mitigate the malware's impact.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with network security concepts and tools.

**Scenario Duration:** 2 hours

---

#### ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- You have sudo privileges on the entry host.
- You can SSH to other hosts within the network using the provided credentials.

**Reachable Hosts:**
- c2-server (IP: 192.168.40.5)
- next-target (IP: 192.168.50.6)

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
Investigate the services running on the target host and identify any suspicious services that might be related to the Kobalos malware.

**Steps:**
1. SSH into the target host using the provided credentials.
2. List all running services using the `systemctl list-units --type=service` command.
3. Look for any suspicious services, especially those that are not part of the standard system services.
4. Identify the service name that appears to be related to the Kobalos malware.

**Flag:** service name

**Hint:**
- Pay attention to services that are not part of the standard system services.
- Look for services that have unusual names or descriptions.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Lateral Movement

**Description:**
Investigate the lateral movement activities between the target host and the next-target host. Identify the service or mechanism used for transferring data between these hosts.

**Steps:**
1. SSH into the target host using the provided credentials.
2. Check the system logs for any suspicious activities related to data transfer.
3. Look for any scripts or services that are responsible for transferring data to the next-target host.
4. Identify the service or mechanism used for lateral movement.

**Flag:** service name

**Hint:**
- Check the `/var/log/syslog` file for any suspicious activities.
- Look for any scripts or services that are responsible for transferring data to the next-target host.

---

#### TRAINING_LEVEL 3
**Task:** Contain C2 Communication

**Description:**
Identify and contain the command and control (C2) communication between the target host and the c2-server host. Block the C2 communication to prevent further malware activities.

**Steps:**
1. SSH into the target host using the provided credentials.
2. Check the network connections using the `netstat -tuln` command.
3. Identify the C2 IP address and port used for communication.
4. Block the C2 communication using the `iptables` command.

**Flag:** Port number

**Hint:**
- Look for any unusual network connections to the c2-server host.
- Use the `iptables` command to block the identified port.

---

### Conclusion
By completing these tasks, you will have identified and mitigated the Kobalos malware's presence in the network. This exercise will help you develop your incident response skills and prepare you for real-world cybersecurity challenges.