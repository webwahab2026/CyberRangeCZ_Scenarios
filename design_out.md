### INFO_LEVEL
**Scenario Title:** XOR.DDoS Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux-based host that has been infected with the XOR.DDoS malware. This malware is known to force infected hosts to participate in large DDoS attack campaigns. Your goal is to identify and analyze the malicious activities on the compromised host, understand the malware's behavior, and gather evidence for further investigation.

**Scenario Learning Objectives:**
- Identify suspicious services and their associated network ports.
- Analyze systemd timers and services to understand persistence mechanisms.
- Investigate lateral movement activities and unauthorized file transfers.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. List all services, including inactive ones:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. Identify the suspicious service. In this case, the service name is `bkd.service`.

**Hidden Flag:**
The service name is `bkd.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. The suspicious service is related to network communication.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. Check the status of the suspicious service identified in the previous task:
   ```bash
   systemctl status bkd.service
   ```
3. Examine the service configuration to find the port number:
   ```bash
   systemctl cat bkd.service
   ```
4. Look for the `ExecStart` line in the service configuration. The port number is specified as an argument to the command.
5. The port number is `4444`.

**Hidden Flag:**
The C2 port number is `4444`.

**Hints:**
1. Use `systemctl status bkd.service` to check the service status.
2. Use `systemctl cat bkd.service` to view the service configuration.
3. Look for the `ExecStart` line to find the port number.

### TRAINING_LEVEL 3
**Task Description:**
Investigate the compromised host to identify the component responsible for transferring files to another host. Unusual file synchronization activity has been detected between systems in the environment.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. List all services, including inactive ones:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for services related to file transfer or synchronization. Pay attention to services with unusual names or those that are not part of standard system services.
4. Identify the suspicious service. In this case, the service name is `payload-transfer.service`.
5. Check the status of the suspicious service:
   ```bash
   systemctl status payload-transfer.service
   ```
6. Examine the service configuration to understand its behavior:
   ```bash
   systemctl cat payload-transfer.service
   ```
7. The service is responsible for transferring files to `next-target`.

**Hidden Flag:**
The service name is `payload-transfer.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services related to file transfer or synchronization.
3. Use `systemctl status payload-transfer.service` to check the service status.
4. Use `systemctl cat payload-transfer.service` to view the service configuration.