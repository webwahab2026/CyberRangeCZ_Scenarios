### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network infected with the Remaiten botnet. This botnet targets Linux-based systems, including routers and IoT devices. Your goal is to identify and analyze the malicious activities, understand the botnet's behavior, and gather evidence for further remediation.

**Learning Objectives:**
- Identify suspicious services and their behaviors.
- Analyze network communication patterns.
- Investigate persistence mechanisms.
- Gather evidence for further analysis and remediation.

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL
**Task 1: Suspicious C2 Beacon Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will list all services, including inactive ones. Look for any unfamiliar or suspicious service names.

2. **Check the status of all services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This command will show you the currently running services. Look for any services that seem out of place or have unusual descriptions.

3. **Inspect network connections:**
   ```bash
   ss -tunap
   ```
   This command will display all network connections. Look for any connections to external IPs or unusual ports.

4. **Identify the suspicious service:**
   From the list of services, identify the one that is responsible for sending beacons to the C2 server. This service will likely have an unusual name or description.

**Hidden Flag:** bot-beacon.service

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services and look for any unfamiliar or suspicious service names.

**Hint 2:**
Check the status of all services using `systemctl list-units --type=service --state=running` to identify any running services that seem out of place.

**Hint 3:**
Inspect network connections with `ss -tunap` to look for any connections to external IPs or unusual ports.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the suspicious service:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will show you the configuration of the `bot-beacon.service`. Look for the `ExecStart` line to find the path of the script launched by the service.

2. **Examine the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This script contains the details of the communication with the C2 server. Look for the `c2_port` variable to find the port number.

**Hidden Flag:** 53

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the configuration of the suspicious service and find the path of the script launched by the service.

**Hint 2:**
Examine the beacon script at `/usr/local/lib/.botcache/beacon.sh` to find the `c2_port` variable and determine the port number.

**Hint 3:**
Look for the `ExecStart` line in the service configuration to find the path of the script launched by the service.

---

### TRAINING_LEVEL
**Task 3: Persistence Discovery for C2 Beaconing Service**

**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones. Look for any timers associated with the `bot-beacon.service`.

2. **Inspect the timer configuration:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This command will show you the configuration of the `bot-beacon.timer`. Look for the `OnCalendar` line to understand the scheduling.

3. **Check the status of the timer:**
   ```bash
   systemctl status bot-beacon.timer
   ```
   This command will show you the current status of the timer and its scheduling details.

**Hidden Flag:** bot-beacon.timer

**Hint 1:**
Use `systemctl list-timers --all` to list all timers and look for any timers associated with the `bot-beacon.service`.

**Hint 2:**
Inspect the timer configuration with `systemctl cat bot-beacon.timer` to understand the scheduling details.

**Hint 3:**
Check the status of the timer using `systemctl status bot-beacon.timer` to see its current status and scheduling details.