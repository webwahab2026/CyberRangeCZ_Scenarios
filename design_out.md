### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that appears to be infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activity, understand the backdoor's behavior, and take appropriate containment measures.

**Learning Objectives:**
- Identify suspicious services and their associated files.
- Analyze network communication patterns.
- Investigate persistence mechanisms.
- Contain the threat without disrupting legitimate services.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL
**Task 1: Suspicious Service Discovery**

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
   systemctl cat ksysdefd.service
   ```
   This command will show the service configuration file, which includes the ExecStart command that launches the service.

4. **Identify the service name:**
   The service name is `ksysdefd.service`.

**Hidden Flag:** `ksysdefd.service`

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter the list to show only running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Inspect the suspicious service configuration with `systemctl cat <service>`.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the suspicious service configuration:**
   ```bash
   systemctl cat ksysdefd.service
   ```
   Look for the `ExecStart` line, which specifies the command launched by the service.

2. **Identify the port number:**
   The `ExecStart` line includes the port number as an argument. In this case, it is `80`.

**Hidden Flag:** `80`

**Hint 1:**
Use `systemctl cat <service>` to inspect the service configuration file.

**Hint 2:**
Look for the `ExecStart` line in the service configuration file.

**Hint 3:**
The port number is specified as an argument in the `ExecStart` command.

---

### TRAINING_LEVEL
**Task 3: Persistence Discovery for Data Collection Service**

**Task Description:**
Investigators suspect that unauthorized activity automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

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

3. **Inspect the suspicious timer:**
   ```bash
   systemctl cat local-inventory.timer
   ```
   This command will show the timer configuration file, which includes the schedule and the service it triggers.

4. **Identify the timer name:**
   The timer name is `local-inventory.timer`.

**Hidden Flag:** `local-inventory.timer`

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter the list to show only active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Inspect the suspicious timer configuration with `systemctl cat <timer>`.