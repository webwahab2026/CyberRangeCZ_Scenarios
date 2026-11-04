### INFO_LEVEL
**Scenario Title:** Mirai Trojan Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on a compromised Linux host. Your task is to investigate the Mirai Trojan infection, identify its components, and understand its behavior. The Mirai Trojan is known for conducting DDoS attacks by infecting IoT devices and using them as part of a botnet.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service activation to identify persistence mechanisms.
- Analyze network communication to determine the C2 server's port and IP address.
- Discover how the trojan was initially deployed on the system.

### ACCESS_LEVEL
**Entry Host:** victim
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity of periodically collecting `/etc/passwd`, home directory listings, and sensitive files, then exfiltrating them to a C2 server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   - Use the command `systemctl list-units --type=service --all` to list all services.
   - Look for unfamiliar service names or misspellings of legitimate services.
   - Use `systemctl status <service>` to check the status and description of each service.

2. **Identify Suspicious Service:**
   - The service responsible for the suspicious activity is likely to have an unusual description or startup behavior.
   - Look for services with names like `dvrHelper.timer` or `network-diagnostics.timer`.

3. **Verify the Service:**
   - Use `systemctl cat <service>` to view the service configuration.
   - Check the `ExecStart` field to see if it points to a script that collects and exfiltrates data.

**Hidden Flag:** dvrHelper.timer

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual descriptions or startup behavior.
3. Use `systemctl cat <service>` to view the service configuration.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the Suspicious Service:**
   - From the previous task, you identified the service `dvrHelper.timer`.
   - Use `systemctl cat dvrHelper.timer` to view the timer configuration.

2. **Find the Port Number:**
   - The timer configuration points to a service unit file. Use `systemctl cat dvrHelper.service` to view the service configuration.
   - Look for the `ExecStart` field, which specifies the path to the script launched by the service.
   - Use `cat /usr/local/lib/.netd/harvester.sh` to view the script and find the port number.

**Hidden Flag:** 5556

**Hints:**
1. Use `systemctl cat dvrHelper.timer` to view the timer configuration.
2. Look for the `ExecStart` field in the service unit file.
3. Use `cat /usr/local/lib/.netd/harvester.sh` to find the port number.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the Credential Harvester Service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **Identify the Persistence Mechanism:**
   - Use `systemctl list-timers --all` to list all timers.
   - Look for timers associated with the suspicious service identified in the previous tasks.

2. **Verify the Timer:**
   - Use `systemctl cat dvrHelper.timer` to view the timer configuration.
   - Check the `OnCalendar` field to see the schedule for the timer.

**Hidden Flag:** dvrHelper.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the suspicious service.
3. Use `systemctl cat dvrHelper.timer` to view the timer configuration.