### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the target host, potentially indicating the presence of the Sofacy Fysbis backdoor. Your task is to investigate the compromised host, identify the malicious components, and take appropriate defensive actions.

**Learning Objectives:**
- Enumerate running services and identify suspicious components.
- Investigate network communication and data exfiltration.
- Analyze persistence mechanisms and lateral movement techniques.
- Apply containment and remediation measures.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with systemd and network services.
- Understanding of basic cybersecurity concepts.

---

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Network Topology:**
- **target (192.168.50.5):** Compromised host with suspicious activity.
- **next-target (192.168.50.6):** Potential lateral movement target.
- **c2-server (192.168.40.5):** External command and control server.

**Tools Available:**
- Standard Linux command-line tools (e.g., `systemctl`, `ss`, `ps`, `journalctl`, `ncat`, `iptables`).
- SSH access to investigate the compromised host and potential lateral movement target.

---

### TRAINING_LEVEL
**Task 1: Suspicious C2 Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will display all services, including inactive ones. Look for any unfamiliar or suspicious service names.

2. **Check the status of the suspicious service:**
   ```bash
   systemctl status ksysdefd.service
   ```
   This command will provide details about the service, including its description, execution command, and status.

3. **Inspect the service configuration:**
   ```bash
   systemctl cat ksysdefd.service
   ```
   This command will display the service unit file, which contains the service definition and execution command.

4. **Identify the service name:**
   From the service unit file, you can see that the service name is `ksysdefd.service`.

**Hidden Flag:**
The hidden flag is the service name: `ksysdefd.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services and look for any unfamiliar or suspicious service names.

**Hint 2:**
Check the status of the suspicious service using `systemctl status <service>`.

**Hint 3:**
Inspect the service configuration using `systemctl cat <service>` to understand its behavior and execution command.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **List all listening ports:**
   ```bash
   ss -tulnp
   ```
   This command will display all listening ports and the associated processes.

2. **Identify the port used by the suspicious service:**
   From the output of the previous command, you can see that the `ksysdefd.service` is listening on port `80`.

3. **Verify the port in the service configuration:**
   ```bash
   systemctl cat ksysdefd.service
   ```
   This command will display the service unit file, which contains the port number in the `ExecStart` command.

**Hidden Flag:**
The hidden flag is the C2 port number: `80`.

**Hint 1:**
Use `ss -tulnp` to list all listening ports and identify the port used by the suspicious service.

**Hint 2:**
Check the service configuration using `systemctl cat <service>` to confirm the port number.

**Hint 3:**
Look for the port number in the `ExecStart` command of the service unit file.

---

### TRAINING_LEVEL
**Task 3: Suspicious Data Collection Service Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all services and timers:**
   ```bash
   systemctl list-units --type=service --all
   systemctl list-timers --all
   ```
   These commands will display all services and timers, including those that run periodically.

2. **Identify the suspicious service:**
   Look for any unfamiliar or suspicious service names in the list. Pay particular attention to services that run periodically.

3. **Check the status of the suspicious service:**
   ```bash
   systemctl status local-inventory.service
   ```
   This command will provide details about the service, including its description, execution command, and status.

4. **Inspect the service configuration:**
   ```bash
   systemctl cat local-inventory.service
   ```
   This command will display the service unit file, which contains the service definition and execution command.

**Hidden Flag:**
The hidden flag is the service name: `local-inventory.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` and `systemctl list-timers --all` to list all services and timers.

**Hint 2:**
Check the status of the suspicious service using `systemctl status <service>`.

**Hint 3:**
Inspect the service configuration using `systemctl cat <service>` to understand its behavior and execution command.