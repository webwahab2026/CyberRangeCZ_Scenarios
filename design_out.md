### INFO_LEVEL
**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network where the Remaiten botnet malware has been detected. The malware targets routers and IoT devices, combining capabilities of Tsunami (Kaiten) and Gafgyt with improvements and new features. Your goal is to identify and contain the malicious activities associated with this botnet.

**Learning Objectives:**
- Identify suspicious services and their associated network ports.
- Discover persistence mechanisms used by the malware.
- Investigate unauthorized data collection and communication activities.
- Apply appropriate containment measures to prevent further malicious activities.

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
   This command will list all services, including those that are inactive or failed.

2. **Filter for active services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This command will show you the services that are currently running.

3. **Inspect the suspicious service:**
   Look for any unfamiliar or suspicious service names. For example, you might see a service named `bot-beacon.service`.

4. **Check the service details:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will display the service configuration file, which can provide more information about the service.

5. **Verify the service status:**
   ```bash
   systemctl status bot-beacon.service
   ```
   This command will show you the status of the service, including recent logs and activity.

6. **Identify the hidden flag:**
   The hidden flag is the name of the suspicious service. In this case, it is `bot-beacon.service`.

**Hidden Flag:**
`bot-beacon.service`

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual or unfamiliar names, as these could be indicators of malicious activity.

**Hint 3:**
Use `systemctl cat <service>` to inspect the configuration file of a suspicious service.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **List all listening ports:**
   ```bash
   ss -tulnp
   ```
   This command will show you all listening ports and the associated processes.

2. **Identify the suspicious service:**
   Look for the service you identified in Task 1 (`bot-beacon.service`) and note the port it is listening on.

3. **Inspect the service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will display the service configuration file, which can provide more information about the service.

4. **Check the ExecStart line:**
   Look for the `ExecStart` line in the service configuration file. This line specifies the path of the script launched by the service.

5. **Inspect the script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This command will display the contents of the script, which can provide more information about the communication port.

6. **Identify the hidden flag:**
   The hidden flag is the network port associated with the C2 communication. In this case, it is `53`.

**Hidden Flag:**
`53`

**Hint 1:**
Use `ss -tulnp` to list all listening ports and the associated processes.

**Hint 2:**
Look for the service you identified in Task 1 and note the port it is listening on.

**Hint 3:**
Use `systemctl cat <service>` to inspect the service configuration file and look for the `ExecStart` line.

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
   This command will list all timers, including those that are inactive or failed.

2. **Filter for active timers:**
   ```bash
   systemctl list-timers --state=active
   ```
   This command will show you the timers that are currently active.

3. **Inspect the suspicious timer:**
   Look for any unfamiliar or suspicious timer names. For example, you might see a timer named `bot-beacon.timer`.

4. **Check the timer details:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This command will display the timer configuration file, which can provide more information about the timer.

5. **Verify the timer status:**
   ```bash
   systemctl status bot-beacon.timer
   ```
   This command will show you the status of the timer, including recent logs and activity.

6. **Identify the hidden flag:**
   The hidden flag is the name of the suspicious timer. In this case, it is `bot-beacon.timer`.

**Hidden Flag:**
`bot-beacon.timer`

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Look for timers with unusual or unfamiliar names, as these could be indicators of malicious activity.

**Hint 3:**
Use `systemctl cat <timer>` to inspect the configuration file of a suspicious timer.