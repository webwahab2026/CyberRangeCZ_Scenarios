### Scenario: Linux/AirDropBot Botnet Investigation

**INFO_LEVEL**
Linux/AirDropBot is a multiplatform Linux malware that functions as a backdoor and botnet. It has infection capabilities targeting vulnerabilities in routers CGI or telnet. The malware can perform TCP, UDP, and custom pattern DDoS attacks. It connects to a C2 server to receive commands and can spread via exploiting vulnerabilities.

**ACCESS_LEVEL**
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. Log in to the bot1 host using the provided credentials.
2. List all services to identify any unusual or suspicious services.
   - Command: `systemctl list-units --type=service --all`
3. Look for services with unusual names or descriptions that might indicate malicious activity.
4. Identify the service responsible for sending beacon to the C2 server.

**Hint 1:**
Use the `systemctl` command to list all services and look for any that seem out of place.

**Hint 2:**
Check the service descriptions and paths to identify any suspicious services.

**Hint 3:**
Look for services that might be related to network communication or system health monitoring.

**Hidden Flag:**
bot-beacon-cloudprocess.service

**TRAINING_LEVEL 2**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Log in to the bot1 host using the provided credentials.
2. Inspect the service identified in the previous task to find the network port associated with the communication.
   - Command: `systemctl cat bot-beacon-cloudprocess.service`
3. Look for the `ExecStart` line in the service file to identify the script path.
4. Examine the script to find the network port used for communication.
   - Command: `cat /usr/local/lib/.botcache/beacon.sh`

**Hint 1:**
Use the `systemctl cat` command to view the service configuration.

**Hint 2:**
Look for the `ExecStart` line in the service file to identify the script path.

**Hint 3:**
Examine the script to find the network port used for communication.

**Hidden Flag:**
455

**TRAINING_LEVEL 3**
**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. Log in to the bot1 host using the provided credentials.
2. List all timers to identify any unusual or suspicious timers.
   - Command: `systemctl list-timers --all`
3. Look for timers with unusual names or descriptions that might indicate malicious activity.
4. Identify the timer responsible for scheduling the C2 beacon service.

**Hint 1:**
Use the `systemctl list-timers --all` command to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions that might indicate malicious activity.

**Hint 3:**
Identify the timer responsible for scheduling the C2 beacon service.

**Hidden Flag:**
bot-beacon-cloudprocess.timer