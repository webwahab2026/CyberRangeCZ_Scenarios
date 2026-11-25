### INFO_LEVEL
**Scenario Title:** Gafgyt Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network where Gafgyt botnet malware has been detected. Your goal is to identify and analyze the malicious activities, understand the infection vector, and gather evidence for further remediation.

**Learning Objectives:**
- Identify suspicious services and their behaviors.
- Analyze network communication patterns.
- Investigate persistence mechanisms.
- Gather evidence for further analysis.

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
   This command will list all services, including inactive ones. Look for any unfamiliar or suspicious service names.

2. **Check the status of the suspicious service:**
   ```bash
   systemctl status bot-beacon.service
   ```
   This command will provide details about the service, including its description and recent logs.

3. **Inspect the service configuration:**
   ```bash
   systemctl cat bot-beacon.service
   ```
   This command will show the service unit file, which contains information about the service's execution and dependencies.

4. **Identify the service responsible for beaconing:**
   From the service configuration, you can see that the service named `bot-beacon.service` is responsible for sending periodic beacons to the C2 server.

**Hidden Flag:**
The hidden flag is the name of the service responsible for beaconing: `bot-beacon.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Check the status of suspicious services with `systemctl status <service>`.
3. Inspect the service configuration with `systemctl cat <service>`.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **List all listening ports:**
   ```bash
   ss -tunap
   ```
   This command will list all listening ports and the processes using them.

2. **Identify the process using the suspicious port:**
   From the output, you can see that the process `/usr/local/lib/.botcache/beacon.sh` is using port `2222`.

3. **Inspect the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This script will show the port number used for communication with the C2 server.

4. **Determine the network port:**
   From the beacon script, you can see that the port number used for communication is `2222`.

**Hidden Flag:**
The hidden flag is the network port associated with the communication: `2222`.

**Hints:**
1. Use `ss -tunap` to list all listening ports and processes.
2. Identify the process using the suspicious port.
3. Inspect the beacon script to find the port number.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones. Look for any unfamiliar or suspicious timer names.

2. **Check the status of the suspicious timer:**
   ```bash
   systemctl status bot-beacon.timer
   ```
   This command will provide details about the timer, including its description and recent logs.

3. **Inspect the timer configuration:**
   ```bash
   systemctl cat bot-beacon.timer
   ```
   This command will show the timer unit file, which contains information about the timer's schedule and dependencies.

4. **Identify the timer responsible for scheduling the beacon service:**
   From the timer configuration, you can see that the timer named `bot-beacon.timer` is responsible for scheduling the `bot-beacon.service`.

**Hidden Flag:**
The hidden flag is the name of the timer responsible for scheduling the beacon service: `bot-beacon.timer`.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Check the status of suspicious timers with `systemctl status <timer>`.
3. Inspect the timer configuration with `systemctl cat <timer>`.