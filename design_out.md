### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that appears to be infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activities, understand the backdoor's behavior, and gather evidence for further investigation.

**Learning Objectives:**
- Identify suspicious services and their behavior.
- Analyze network communication for signs of command and control (C2) activity.
- Investigate file transfers and lateral movement indicators.
- Understand the persistence mechanisms used by the backdoor.

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
   systemctl status ksysdefd.service
   ```
   This will provide details about the service, including its description and the command it runs.

4. **Inspect the service configuration:**
   ```bash
   systemctl cat ksysdefd.service
   ```
   This will show the service unit file, which contains the service definition and the command it executes.

5. **Identify the service responsible for the suspicious activity:**
   The service name is `ksysdefd.service`.

**Hidden Flag:** `ksysdefd.service`

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Check the status of the suspicious service with `systemctl status ksysdefd.service`.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the service configuration:**
   ```bash
   systemctl cat ksysdefd.service
   ```
   This will show the service unit file, which contains the service definition and the command it executes.

2. **Identify the port number:**
   Look for the `ExecStart` line in the service unit file. The port number is specified as an argument to the command.

3. **Verify the port with network listeners:**
   ```bash
   ss -tulnp
   ```
   This command will list all network listeners and their associated processes. Look for the port number identified in the previous step.

4. **Determine the network port associated with the communication:**
   The port number is `80`.

**Hidden Flag:** `80`

**Hint 1:**
Use `systemctl cat ksysdefd.service` to inspect the service configuration.

**Hint 2:**
Look for the `ExecStart` line in the service unit file to identify the port number.

**Hint 3:**
Verify the port with network listeners using `ss -tulnp`.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the suspicious data collection service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

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
   systemctl status payload-transfer.timer
   ```
   This will provide details about the timer, including its description and the service it triggers.

4. **Inspect the timer configuration:**
   ```bash
   systemctl cat payload-transfer.timer
   ```
   This will show the timer unit file, which contains the timer definition and the service it triggers.

5. **Determine the timer responsible for scheduling the activity:**
   The timer name is `payload-transfer.timer`.

**Hidden Flag:** `payload-transfer.timer`

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter for active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Check the status of the suspicious timer with `systemctl status payload-transfer.timer`.