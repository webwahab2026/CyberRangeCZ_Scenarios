### INFO_LEVEL

**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network infected with the Mirai botnet. Your goal is to identify and contain the malicious activities, including C2 communication, data collection, and flood attacks.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service activation and scheduling to identify persistence mechanisms.
- Correlate network connections and service behavior to identify unauthorized communication and data exfiltration.
- Apply appropriate network controls to contain the threat.
- Terminate malicious processes and remove persistence mechanisms.
- Verify the effectiveness of containment and remediation efforts.

### ACCESS_LEVEL

**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   - Use the command `systemctl list-units --type=service --state=running` to list all running services.
   - Look for any unfamiliar or suspicious service names.

2. **Check Service Details:**
   - Use the command `systemctl status <service_name>` to get detailed information about the suspicious service.
   - Look for any unusual descriptions or startup behavior.

3. **Identify the Beacon Service:**
   - The service responsible for sending beacon periodically to the C2 Server is likely to have a name related to "beacon" or "health check."
   - Use the command `systemctl cat <service_name>` to inspect the service definition and confirm its behavior.

**Hidden Flag:** bot-beacon.service

**Hints:**
1. Use `systemctl list-units --type=service --state=running` to list all running services.
2. Look for any unfamiliar or suspicious service names.
3. Use `systemctl status <service_name>` to get detailed information about the suspicious service.

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the Suspicious Service:**
   - Use the command `systemctl list-units --type=service --all` to list all services.
   - Look for any unfamiliar or suspicious service names.

2. **Inspect the Service Definition:**
   - Use the command `systemctl cat <service_name>` to inspect the service definition.
   - Pay particular attention to the `ExecStart` line, which specifies the path of the script launched by the service.

3. **Check the Script for Communication Port:**
   - Navigate to the script path specified in the `ExecStart` line.
   - Use a text editor or `cat` command to view the script and identify the communication port with the C2 server.

**Hidden Flag:** 2222

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for any unfamiliar or suspicious service names.
3. Use `systemctl cat <service_name>` to inspect the service definition and identify the communication port.

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List All Timers:**
   - Use the command `systemctl list-timers --all` to list all timers.
   - Look for any unfamiliar or suspicious timer names.

2. **Inspect the Timer Definition:**
   - Use the command `systemctl cat <timer_name>` to inspect the timer definition.
   - Pay particular attention to the `OnCalendar` line, which specifies the schedule for the timer.

3. **Verify the Timer Status:**
   - Use the command `systemctl status <timer_name>` to verify the timer status and confirm its behavior.

**Hidden Flag:** bot-beacon.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for any unfamiliar or suspicious timer names.
3. Use `systemctl cat <timer_name>` to inspect the timer definition and identify the scheduling mechanism.