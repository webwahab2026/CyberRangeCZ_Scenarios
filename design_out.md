### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network that has been infected with the Remaiten botnet malware. Your goal is to identify and analyze the malicious activities performed by the botnet on the infected hosts.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service activation and scheduling to identify persistence mechanisms.
- Correlate network listeners, service configurations, and running processes to identify communication ports.

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
   This command will display all services, including inactive ones.

2. **Filter for running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This will help you identify services that are currently active.

3. **Check service descriptions and paths:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.

4. **Identify the suspicious service:**
   The service responsible for sending beacon to the C2 server is likely to have a name or description that indicates network activity. In this case, the service name is `bot-beacon.service`.

**Hidden Flag:** `bot-beacon.service`

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Look for services with unusual names or descriptions that might indicate network activity.

---

### TRAINING_LEVEL
**Task 2: Persistence Discovery for C2 Beaconing Service**

**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

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
   This will help you identify timers that are currently active.

3. **Inspect the timer unit file:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This command will show the configuration of the timer unit file.

4. **Identify the timer responsible for the C2 beacon service:**
   The timer name is `bot-beacon.timer`.

**Hidden Flag:** `bot-beacon.timer`

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter for active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Inspect the timer unit file using `systemctl cat <timer>`.

---

### TRAINING_LEVEL
**Task 3: Suspicious Flood Service Discovery**

**Task Description:**
Security monitoring has detected an unusual outbound traffic toward an IP address. Investigate the running services and identify the service responsible for attack flooding periodically to the target.

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
   This will help you identify services that are currently active.

3. **Check service descriptions and paths:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.

4. **Identify the suspicious service:**
   The service responsible for sending flood to the target is likely to have a name or description that indicates network activity. In this case, the service name is `bot-flood.service`.

**Hidden Flag:** `bot-flood.service`

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Look for services with unusual names or descriptions that might indicate network activity.