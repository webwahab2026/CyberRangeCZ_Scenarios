### INFO_LEVEL
**Scenario Title:** Gafgyt Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a suspected Gafgyt (BASHLITE) botnet infection on a Linux-based system. Gafgyt is known for compromising IoT devices and Linux systems, often through weak passwords and known vulnerabilities. The malware aims to gain control of these devices and conduct DDoS attacks.

Your mission is to investigate the compromised hosts, identify the malicious activities, and gather evidence of the botnet's presence.

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

2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication or system health monitoring.

3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service identified in the previous step.

4. **Investigate the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   This command will show the service configuration file, which can provide more details about the service's behavior.

5. **Identify the hidden flag:**
   The hidden flag is the name of the suspicious service responsible for sending beacon periodically to the C2 Server.

**Hidden Flag:** bot-beacon.service

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual names or descriptions that might be related to network communication or system health monitoring.

**Hint 3:**
Use `systemctl status <service_name>` to check the status of suspicious services and gather more information.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the suspicious service:**
   From Task 1, you identified the suspicious service `bot-beacon.service`.

2. **Inspect the service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will show the service configuration file.

3. **Locate the ExecStart directive:**
   In the service configuration file, look for the `ExecStart` directive. This specifies the path of the script launched by the service.

4. **Inspect the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This script contains the details of the communication with the C2 server.

5. **Identify the communication port:**
   Within the beacon script, look for the port number used for communication with the C2 server.

**Hidden Flag:** 2222

**Hint 1:**
Use `systemctl cat bot-beacon.service` to inspect the service configuration file.

**Hint 2:**
Look for the `ExecStart` directive in the service configuration file to find the path of the beacon script.

**Hint 3:**
Inspect the beacon script to find the port number used for communication with the C2 server.

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
   This command will list all timers, including inactive ones.

2. **Identify suspicious timers:**
   Look for timers with unusual names or descriptions that might be related to the suspicious service identified in Task 1.

3. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer identified in the previous step.

4. **Identify the hidden flag:**
   The hidden flag is the name of the timer responsible for scheduling the C2 beacon service.

**Hidden Flag:** bot-beacon.timer

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Look for timers with unusual names or descriptions that might be related to the suspicious service identified in Task 1.

**Hint 3:**
Use `systemctl cat <timer_name>` to inspect the timer configuration and gather more information.