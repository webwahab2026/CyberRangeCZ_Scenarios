### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Remaiten botnet infection on a compromised network. The botnet is known to target routers and IoT devices, using telnet scanning to spread and guessing login credentials. Your goal is to identify and analyze the malicious activities on the infected hosts.

**Learning Objectives:**
- Identify suspicious services and their behaviors.
- Analyze network communication patterns.
- Investigate persistence mechanisms.
- Correlate findings to understand the botnet's operations.

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

2. **Filter for active services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This will show only the services that are currently running.

3. **Inspect the suspicious service:**
   Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that you do not recognize as part of the standard system services.

4. **Check the service details:**
   ```bash
   systemctl cat <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service you identified. This command will show the service configuration file, which may contain clues about its behavior.

5. **Examine the service logs:**
   ```bash
   journalctl -u <service_name>
   ```
   This will display the logs associated with the service, which can help you understand its activities.

6. **Identify the beacon service:**
   Based on the service configuration and logs, identify the service responsible for sending beacon periodically to the C2 Server.

**Hidden Flag:**
The service name is `bot-beacon.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Filter for running services with `systemctl list-units --type=service --state=running`.
3. Inspect the suspicious service with `systemctl cat <service_name>`.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the suspicious service:**
   From the previous task, you should have identified the service responsible for sending beacon periodically to the C2 Server. Let's assume it is named `<service_name>`.

2. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   This will show the service configuration file, which may contain the port number used for communication.

3. **Check the service logs:**
   ```bash
   journalctl -u <service_name>
   ```
   This will display the logs associated with the service, which can help you understand its activities and the port used for communication.

4. **List all network connections:**
   ```bash
   ss -tunap
   ```
   This command will display all network connections, including the port used by the suspicious service.

5. **Identify the communication port:**
   Based on the service configuration, logs, and network connections, identify the network port associated with the unauthorized communication.

**Hidden Flag:**
The C2 port number is `53`.

**Hints:**
1. Use `systemctl cat <service_name>` to inspect the service configuration.
2. Check the service logs with `journalctl -u <service_name>`.
3. List all network connections with `ss -tunap`.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

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
   This will show only the timers that are currently active.

3. **Inspect the suspicious timer:**
   Look for any unfamiliar or suspicious timer names. Pay attention to timers with unusual descriptions or those that you do not recognize as part of the standard system timers.

4. **Check the timer details:**
   ```bash
   systemctl cat <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer you identified. This command will show the timer configuration file, which may contain clues about its behavior.

5. **Examine the timer logs:**
   ```bash
   journalctl -u <timer_name>
   ```
   This will display the logs associated with the timer, which can help you understand its activities.

6. **Identify the timer responsible for scheduling the C2 beacon service:**
   Based on the timer configuration and logs, identify the timer responsible for scheduling the C2 beacon service.

**Hidden Flag:**
The timer name is `bot-beacon.timer`.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Filter for active timers with `systemctl list-timers --state=active`.
3. Inspect the suspicious timer with `systemctl cat <timer_name>`.