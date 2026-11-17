### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network where the Remaiten botnet malware has been detected. Your goal is to identify and analyze the malicious activities, understand the botnet's behavior, and take appropriate containment measures.

**Learning Objectives:**
- Identify suspicious services and their behavior.
- Analyze network communication patterns.
- Investigate persistence mechanisms.
- Contain the threat effectively.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will list all services, including inactive ones.

2. **Filter for suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication or system health monitoring.

3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service identified in the previous step.

4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   This will show the service unit file, which contains details about the service, including the executable path and any associated timers.

5. **Identify the beacon service:**
   The beacon service is likely to have a name related to system health or network diagnostics. Look for services that are periodically executed and have network-related descriptions.

6. **Hidden Flag:**
   The service name is `bot-beacon.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services and look for any that seem unusual or related to network communication.

**Hint 2:**
Check the status of suspicious services using `systemctl status <service_name>` to see if they are periodically executed.

**Hint 3:**
Inspect the service configuration with `systemctl cat <service_name>` to understand its behavior and identify the beacon service.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the beacon service:**
   From the previous task, you identified the beacon service as `bot-beacon.service`.

2. **Inspect the beacon service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This will show the service unit file, which contains details about the service, including the executable path.

3. **Examine the beacon script:**
   The service unit file will point to a script, likely located in `/usr/local/lib/.botcache/beacon.sh`. Open and examine this script to find the network port used for communication.

4. **Look for the port number:**
   In the beacon script, look for the `nc` (netcat) command. The port number will be specified as the second argument to this command.

5. **Hidden Flag:**
   The C2 port number is `53`.

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the beacon service configuration and find the path to the beacon script.

**Hint 2:**
Open the beacon script located in `/usr/local/lib/.botcache/beacon.sh` and look for the `nc` command to find the port number.

**Hint 3:**
The port number is specified as the second argument to the `nc` command in the beacon script.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones.

2. **Identify the timer associated with the beacon service:**
   Look for a timer with a name related to the beacon service, such as `bot-beacon.timer`.

3. **Inspect the timer configuration:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This will show the timer unit file, which contains details about the timer, including the schedule and the service it triggers.

4. **Verify the timer status:**
   ```bash
   systemctl status bot-beacon.timer
   ```
   This will show the current status of the timer and confirm that it is active and scheduling the beacon service as expected.

5. **Hidden Flag:**
   The timer name is `bot-beacon.timer`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers and look for any that seem related to the beacon service.

**Hint 2:**
Inspect the timer configuration with `systemctl cat bot-beacon.timer` to understand its schedule and the service it triggers.

**Hint 3:**
Verify the timer status using `systemctl status bot-beacon.timer` to confirm that it is active and scheduling the beacon service.