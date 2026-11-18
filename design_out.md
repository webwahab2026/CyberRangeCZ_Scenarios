### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network infected with the Remaiten botnet. Your goal is to identify and analyze the malicious activities performed by the botnet on the infected hosts. The botnet is known to perform command and control (C2) communication, lateral movement, and exfiltration of data.

**Learning Objectives:**
- Identify suspicious services and their associated network ports.
- Analyze systemd timers and services for persistence mechanisms.
- Investigate unauthorized network communication and data collection activities.

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
1. Connect to the bot1 host using SSH with the provided credentials.
2. List all services to identify any suspicious or unfamiliar services.
   ```
   systemctl list-units --type=service --all
   ```
3. Check the status of all services to find any unusual or suspicious services.
   ```
   systemctl list-units --type=service --state=running
   ```
4. Look for services with unusual names or descriptions that might indicate malicious activity.
5. Identify the service responsible for sending beacon periodically to the C2 Server.

**Hint 1:**
Use the `systemctl` command to list all services and look for any unfamiliar or suspicious service names.

**Hint 2:**
Check the status of all running services to identify any unusual or suspicious services.

**Hint 3:**
Look for services with unusual names or descriptions that might indicate malicious activity.

**Hidden Flag:**
The service name is `bot-beacon.service`.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Connect to the bot1 host using SSH with the provided credentials.
2. Inspect the service configuration to find the network port associated with the C2 communication.
   ```
   systemctl cat bot-beacon.service
   ```
3. Check the ExecStart line in the service configuration to identify the script responsible for the C2 communication.
4. Inspect the script to find the network port used for the C2 communication.
   ```
   cat /usr/local/lib/.botcache/beacon.sh
   ```
5. Identify the network port associated with the C2 communication.

**Hint 1:**
Use the `systemctl cat` command to inspect the service configuration and find the network port.

**Hint 2:**
Check the ExecStart line in the service configuration to identify the script responsible for the C2 communication.

**Hint 3:**
Inspect the script to find the network port used for the C2 communication.

**Hidden Flag:**
The C2 port number is `53`.

---

### TRAINING_LEVEL
**Task 3: Persistence Discovery for C2 Beaconing Service**

**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. Connect to the bot1 host using SSH with the provided credentials.
2. List all timers to identify any suspicious or unfamiliar timers.
   ```
   systemctl list-timers --all
   ```
3. Check the status of all timers to find any unusual or suspicious timers.
   ```
   systemctl list-unit-files --type=timer
   ```
4. Look for timers with unusual names or descriptions that might indicate malicious activity.
5. Identify the timer responsible for scheduling the C2 beacon service.

**Hint 1:**
Use the `systemctl list-timers` command to list all timers and look for any unfamiliar or suspicious timer names.

**Hint 2:**
Check the status of all timers to identify any unusual or suspicious timers.

**Hint 3:**
Look for timers with unusual names or descriptions that might indicate malicious activity.

**Hidden Flag:**
The timer name is `bot-beacon.timer`.