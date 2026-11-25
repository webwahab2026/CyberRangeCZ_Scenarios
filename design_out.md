### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux system infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activities, understand the backdoor's behavior, and gather evidence for further remediation.

**Learning Objectives:**
- Identify suspicious services and their associated ports.
- Analyze systemd timers and services for persistence mechanisms.
- Investigate lateral movement activities and data exfiltration.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will display all services, including inactive ones.

2. **Filter for active services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   Look for any unfamiliar or suspicious service names.

3. **Inspect the suspicious service:**
   ```bash
   systemctl status systemkernelservicedefender.service
   ```
   This command provides detailed information about the service, including its description, execution command, and status.

4. **Identify the service name:**
   From the output of the previous command, note the service name `systemkernelservicedefender.service`.

**Hidden Flag:**
The hidden flag is the name of the suspicious service: `systemkernelservicedefender.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter the list of services to show only running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Inspect the suspicious service in detail with `systemctl status <service_name>`.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the suspicious service configuration:**
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```
   This command displays the service unit file, which contains the configuration details.

2. **Identify the port number:**
   Look for the `ExecStart` line in the service unit file. The port number is specified as an argument to the `ncat` command.

3. **Verify the port with network listeners:**
   ```bash
   ss -tulnp
   ```
   This command lists all network listeners and their associated processes. Confirm that the port identified in the service configuration is indeed being used by the suspicious service.

**Hidden Flag:**
The hidden flag is the network port number used by the suspicious service: `80`.

**Hint 1:**
Use `systemctl cat <service_name>` to view the service configuration file.

**Hint 2:**
Look for the `ExecStart` line in the service unit file to find the port number.

**Hint 3:**
Verify the port with `ss -tulnp` to confirm the network listener.

### TRAINING_LEVEL 3
**Task Description:**
Investigate the compromised host to identify the component responsible for transferring files to another host. Unusual file synchronization activity has been detected between systems in the environment.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   Look for any unfamiliar or suspicious service names.

2. **Inspect the suspicious service:**
   ```bash
   systemctl status payload-transfer.service
   ```
   This command provides detailed information about the service, including its description, execution command, and status.

3. **Identify the service name:**
   From the output of the previous command, note the service name `payload-transfer.service`.

**Hidden Flag:**
The hidden flag is the name of the suspicious service: `payload-transfer.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter the list of services to show only running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Inspect the suspicious service in detail with `systemctl status <service_name>`.