### INFO_LEVEL
**Scenario Title:** Gafgyt Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network where Gafgyt botnet malware has been detected. Your goal is to identify and analyze the malicious activities, understand the infection vector, and gather evidence for further remediation.

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

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will list all services, including inactive ones.

2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.

3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service identified in the previous step.

4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   This command will show the service configuration file, which might reveal more details about its behavior.

5. **Identify the beacon service:**
   Look for a service that is responsible for sending periodic beacons to the C2 server. This service will likely have a description or configuration that indicates network communication.

6. **Hidden Flag:**
   The service name is `bot-beacon-wget.service`.

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
1. **Identify the beacon service:**
   From the previous task, you identified the beacon service as `bot-beacon-wget.service`.

2. **Inspect the service configuration:**
   ```bash
   systemctl cat bot-beacon-wget.service
   ```
   This command will show the service configuration file.

3. **Check the ExecStart line:**
   Look for the `ExecStart` line in the service configuration. This line specifies the path of the script launched by the service.

4. **Inspect the beacon script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
   This script contains the details of the communication with the C2 server.

5. **Identify the communication port:**
   Look for the port number in the beacon script. It will be specified in the `nc` command.

6. **Hidden Flag:**
   The C2 port number is `2222`.

**Hint 1:**
Use `systemctl cat bot-beacon-wget.service` to inspect the service configuration.

**Hint 2:**
Look for the `ExecStart` line in the service configuration to find the path of the beacon script.

**Hint 3:**
Use `cat /usr/local/lib/.botcache/beacon.sh` to inspect the beacon script and find the communication port.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones.

2. **Identify suspicious timers:**
   Look for timers with unusual names or descriptions. Pay attention to timers that might be related to the beacon service.

3. **Check the status of suspicious timers:**
   ```bash
   systemctl status <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer identified in the previous step.

4. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
   This command will show the timer configuration file, which might reveal more details about its behavior.

5. **Identify the beacon timer:**
   Look for a timer that is responsible for scheduling the beacon service. This timer will likely have a description or configuration that indicates periodic execution.

6. **Hidden Flag:**
   The timer name is `bot-beacon-wget.timer`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions related to periodic execution.

**Hint 3:**
Use `systemctl status <timer_name>` to check the status of suspicious timers.