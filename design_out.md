### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that appears to be infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activities, understand the backdoor's behavior, and gather evidence for further remediation.

**Learning Objectives:**
- Identify suspicious services and their associated ports.
- Analyze systemd timers and services for persistence mechanisms.
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
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will display all services, including inactive ones.

2. **Filter for running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   Look for any unfamiliar or suspicious service names.

3. **Check the status of the suspicious service:**
   ```bash
   systemctl status systemkernelservicedefender.service
   ```
   This will provide details about the service, including its description and the command it executes.

4. **Identify the service name:**
   From the status output, note the service name `systemkernelservicedefender.service`.

**Hidden Flag:**
The hidden flag is the service name: `systemkernelservicedefender.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Check the status of the suspicious service with `systemctl status <service>`.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Check the service configuration:**
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```
   This command will display the service unit file, which includes the `ExecStart` command.

2. **Identify the port number:**
   In the `ExecStart` command, look for the port number specified as an argument to `ncat`. The port number is `80`.

**Hidden Flag:**
The hidden flag is the C2 port number: `80`.

**Hint 1:**
Use `systemctl cat <service>` to view the service unit file.

**Hint 2:**
Look for the `ExecStart` command in the service unit file.

**Hint 3:**
Identify the port number specified as an argument to `ncat`.

### TRAINING_LEVEL 3
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will display all timers, including inactive ones.

2. **Filter for active timers:**
   ```bash
   systemctl list-timers --state=active
   ```
   Look for any unfamiliar or suspicious timer names.

3. **Check the status of the suspicious timer:**
   ```bash
   systemctl status local-inventory.timer
   ```
   This will provide details about the timer, including its description and the service it triggers.

4. **Identify the timer name:**
   From the status output, note the timer name `local-inventory.timer`.

**Hidden Flag:**
The hidden flag is the timer name: `local-inventory.timer`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter for active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Check the status of the suspicious timer with `systemctl status <timer>`.