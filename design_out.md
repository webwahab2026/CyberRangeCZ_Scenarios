### INFO_LEVEL
**Scenario Title:** XOR.DDoS Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux-based network. The network has been infected with the XOR.DDoS malware, which is known to turn infected hosts into bots participating in large DDoS attack campaigns. Your goal is to identify and analyze the malicious activities on the infected hosts.

**Learning Objectives:**
- Identify suspicious services and their behaviors.
- Discover communication endpoints used by the malware.
- Investigate persistence mechanisms employed by the malware.

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
   This command will list all services, including inactive ones.

2. **Filter for running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This will help you identify services that are currently active.

3. **Check service descriptions and paths:**
   Look for services with unusual names or descriptions. Pay attention to the `ExecStart` path in the service definition.

4. **Identify the suspicious service:**
   The service responsible for sending beacon to the C2 server is likely to have a name that does not match common system services.

**Hidden Flag:** bot-beacon.service

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual names or descriptions that do not match common system services.

**Hint 3:**
Check the `ExecStart` path in the service definition to identify the suspicious service.

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
   This command will show the service definition, including the `ExecStart` path.

2. **Examine the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This script contains the communication details, including the port number.

3. **Identify the C2 port:**
   Look for the port number in the `nc` command within the beacon script.

**Hidden Flag:** 2222

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the service definition.

**Hint 2:**
Examine the beacon script located at `/usr/local/lib/.botcache/beacon.sh`.

**Hint 3:**
Look for the port number in the `nc` command within the beacon script.

---

### TRAINING_LEVEL
**Task 3: Persistence Discovery for C2 Beaconing Service**

**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones.

2. **Filter for active timers:**
   ```bash
   systemctl list-timers --state=active
   ```
   This will help you identify timers that are currently active.

3. **Inspect the timer associated with the beacon service:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This command will show the timer definition, including the `OnCalendar` schedule.

4. **Identify the persistence mechanism:**
   The timer responsible for scheduling the beacon service is likely to have a name that matches the service name with `.timer` appended.

**Hidden Flag:** bot-beacon.timer

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Look for timers with names that match the service name with `.timer` appended.

**Hint 3:**
Use `systemctl cat bot-beacon.timer` to inspect the timer definition.