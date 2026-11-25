### INFO_LEVEL

**Scenario Title:** XOR.DDoS Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux-based host that is part of a botnet. The malware, known as Groundhog, is designed to participate in large DDoS (Distributed Denial of Service) attack campaigns. Your goal is to identify and analyze the malicious activities on the infected host.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service activation and scheduling to identify persistence mechanisms.
- Correlate network listeners, service configurations, and running processes to identify communication ports.

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
   This command will display all services, including inactive ones.

2. **Identify suspicious services:**
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
   This command will show the service unit file, which contains details about the service, including the ExecStart command that launches the service.

5. **Analyze the ExecStart command:**
   The ExecStart command in the service unit file will point to the script or binary responsible for the service. Look for any unusual paths or commands.

6. **Identify the beacon service:**
   Based on the information gathered, identify the service responsible for sending beacon periodically to the C2 Server.

**Hidden Flag:**
The service name is `bot-beacon.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions related to network communication.

**Hint 3:**
Use `systemctl status <service_name>` to check the status of suspicious services.

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will show the service unit file for the beacon service.

2. **Analyze the ExecStart command:**
   The ExecStart command in the service unit file will point to the script responsible for the beacon service. Look for any unusual paths or commands.

3. **Check the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This command will display the contents of the beacon script, which includes the network port used for communication.

4. **Identify the communication port:**
   Within the beacon script, look for the `nc` (netcat) command. The port number will be specified as the second argument to the `nc` command.

**Hidden Flag:**
The C2 port number is `2222`.

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the service configuration.

**Hint 2:**
Look for the `nc` (netcat) command in the beacon script to identify the communication port.

**Hint 3:**
The port number is specified as the second argument to the `nc` command.

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will display all timers, including inactive ones.

2. **Identify suspicious timers:**
   Look for timers with unusual names or descriptions. Pay attention to timers that might be related to network communication or system health monitoring.

3. **Check the status of suspicious timers:**
   ```bash
   systemctl status <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer identified in the previous step.

4. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
   This command will show the timer unit file, which contains details about the timer, including the OnCalendar directive that specifies the schedule.

5. **Analyze the OnCalendar directive:**
   The OnCalendar directive in the timer unit file will specify the schedule for the timer. Look for any unusual schedules or intervals.

6. **Identify the timer responsible for the beacon service:**
   Based on the information gathered, identify the timer responsible for scheduling the C2 beacon service.

**Hidden Flag:**
The timer name is `bot-beacon.timer`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions related to network communication.

**Hint 3:**
Use `systemctl status <timer_name>` to check the status of suspicious timers.