### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Objective:**
Investigate and respond to a BRICKSTORM backdoor infection on the target network. The BRICKSTORM backdoor is a 64-bit ELF executable written in Go, designed to handle environment variables for connection parameters, set up logging, configure a WebSocket connector, create service instances, and define request handlers for different request types. It uses VSOCK proxying, multi-layered web service communication, and varied command execution to obscure its activities. The backdoor uses XOR cipher encryption to hide key strings within its code.

**Background:**
The BRICKSTORM backdoor has been detected on the target network. Your task is to investigate the infection, identify the command and control (C2) infrastructure, and contain the threat.

**Learning Objectives:**
- Identify and investigate suspicious services.
- Detect and analyze service persistence mechanisms.
- Identify and investigate suspicious outbound IP addresses and ports.
- Contain and block C2 communication.
- Kill suspicious services and remove persistence mechanisms.

---

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify and investigate the suspicious service on the target host.

**Description:**
The BRICKSTORM backdoor is known to create a suspicious service on the infected host. Investigate the services running on the target host and identify the suspicious service.

**Steps:**
1. Log in to the target host using SSH.
2. List all running services.
3. Identify the suspicious service related to the BRICKSTORM backdoor.

**Flag:** service name

**Hint:**
- Use systemctl to list all running services.
- Look for services that are not part of the standard system services.

---

#### TRAINING_LEVEL 2
**Task:** Identify and investigate the suspicious outbound IP address and port.

**Description:**
The BRICKSTORM backdoor communicates with a command and control (C2) server. Identify the suspicious outbound IP address and port used by the backdoor.

**Steps:**
1. Investigate the network connections on the target host.
2. Identify the suspicious outbound IP address and port used by the BRICKSTORM backdoor.

**Flag:** C2 IP address and port

**Hint:**
- Use netstat or ss to list all network connections.
- Look for connections to external IP addresses and ports that are not part of the standard network traffic.

---

#### TRAINING_LEVEL 3
**Task:** Contain and block the C2 communication.

**Description:**
To prevent further communication with the C2 server, you need to contain and block the C2 communication. Identify the service responsible for the C2 communication and block it.

**Steps:**
1. Identify the service responsible for the C2 communication.
2. Block the service to prevent further communication with the C2 server.

**Flag:** Port number

**Hint:**
- Use iptables or ufw to block the suspicious port.
- Ensure that the service is stopped and cannot be restarted.

---

### Conclusion
By completing these tasks, you will have successfully investigated and contained the BRICKSTORM backdoor infection on the target network. Your actions will help prevent further damage and ensure the security of the network.