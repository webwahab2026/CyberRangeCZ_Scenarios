### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network where the Remaiten botnet malware has been detected. The malware targets routers and IoT devices, performing telnet scanning to infect new victims and establishing command-and-control (C2) communication. Your goal is to identify and analyze the malicious activities, understand the infection vector, and contain the threat.

**Learning Objectives:**
- Identify suspicious services and their behaviors.
- Analyze systemd timers and services for persistence mechanisms.
- Investigate network communication to uncover C2 channels.
- Discover and remove malicious artifacts.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL
**Task 1: Suspicious Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of standard system services.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Identify the beacon service:**
   The beacon service is likely to have a description related to system health or network diagnostics.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions that do not match standard system services.

**Hint 3:**
Use `systemctl status <service_name>` to check the status and description of suspicious services.

**Hidden Flag:** bot-beacon.service

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the beacon service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
2. **Identify the ExecStart path:**
   The ExecStart field in the service configuration points to the script responsible for the beacon activity.
3. **Examine the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
4. **Identify the C2 port:**
   The beacon script contains the port number used for communication with the C2 server.

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the service configuration.

**Hint 2:**
Look for the ExecStart field in the service configuration to find the path to the beacon script.

**Hint 3:**
Examine the beacon script to find the port number used for communication with the C2 server.

**Hidden Flag:** 53

### TRAINING_LEVEL
**Task 3: Persistence Discovery for C2 Beaconing Service**

**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify the timer associated with the beacon service:**
   Look for timers with names related to the beacon service.
3. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
4. **Identify the timer responsible for scheduling the beacon service:**
   The timer configuration will show the schedule and the service it triggers.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with names related to the beacon service.

**Hint 3:**
Use `systemctl cat <timer_name>` to inspect the timer configuration and identify the service it triggers.

**Hidden Flag:** bot-beacon.timer