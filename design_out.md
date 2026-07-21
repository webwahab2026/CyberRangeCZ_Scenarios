# Kobalos Incident Response Scenario

## INFO_LEVEL

A security incident has been detected on the network. Multiple hosts are exhibiting suspicious behavior, including unauthorized services, unexpected network connections, and file transfers. The initial compromise appears to have occurred on the target host, which is now acting as a pivot point for lateral movement. The security team suspects a multi-stage attack involving a backdoor that provides remote access, credential theft, and data exfiltration capabilities. The compromised system is running a service that communicates with an external command-and-control (C2) server, and evidence suggests the attacker has established persistence and moved laterally to another system.

## ACCESS_LEVEL

Access to the following systems is provided:
- **target** (192.168.50.5): Primary compromised host
- **next-target** (192.168.50.6): Lateral movement target
- **c2-server** (192.168.40.5): External command-and-control server

All hosts are accessible via SSH using the user `cyrano` with password `cyrano`.

## TRAINING_LEVEL

### Task 1: Suspicious Service Discovery

**Challenge Description:**
The security team has identified that the target host is running an unauthorized service that is consuming significant system resources. This service is not part of the standard system configuration and is likely associated with the compromise. Your task is to identify this suspicious service and determine its behavior.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Validation:**
Students must identify the name of the suspicious service running on the target host.

**Hint:**
Look for services that are not part of the standard Ubuntu installation and are consuming unusual resources.

---

### Task 2: C2 Communication Discovery (Port)

**Challenge Description:**
Network monitoring has revealed that the target host is communicating with an external server on a specific port. This communication pattern is consistent with command-and-control activity. Your task is to identify the port used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Validation:**
Students must determine the port number used for C2 communication from the target host.

**Hint:**
Check network connections and listening ports on the target host, and correlate with network traffic logs.

---

### Task 3: Lateral Movement Investigation

**Challenge Description:**
Evidence suggests that the attacker has moved laterally from the target host to the next-target host. This movement is likely accomplished through file transfers or remote execution. Your task is to identify the service or mechanism used for this lateral movement.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Validation:**
Students must identify the service name responsible for the lateral movement between the target and next-target hosts.

**Hint:**
Look for services or processes that are transferring files or executing commands between the two hosts, and check for SSH-based communication patterns.

---