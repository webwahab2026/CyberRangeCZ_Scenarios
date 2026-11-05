### INFO_LEVEL

**Scenario Title:** Linux.Ngioweb Botnet Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity involving multiple Linux web servers in your organization. Initial analysis suggests these systems may be compromised by the Linux.Ngioweb botnet, which is known to operate as a proxy botnet and potentially record traffic passing through infected systems. Your task is to investigate these compromised hosts, identify the malicious components, and implement appropriate containment measures.

**Learning Objectives:**
1. Identify and analyze suspicious services and their behavior
2. Investigate network communication patterns
3. Discover and disable persistence mechanisms
4. Implement appropriate containment measures

**Prerequisites:**
- Basic Linux command line knowledge
- Familiarity with systemd service management
- Understanding of network protocols and ports

**Scenario Duration:** 2 hours

---

### ACCESS_LEVEL

**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Access:**
- SSH access to bot2 from bot1 (passwordless)
- SSH access to c2-server from bot1 (passwordless)

**Network Diagram:**
```
[bot1] 192.168.70.10 ------------------- [c2-server] 192.168.70.5
[bot2] 192.168.70.11 -------------------/
                                      [router] 192.168.70.1
                                      [victim] 192.168.80.100
```

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on bot1. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. Connect to bot1 using SSH with the provided credentials.
2. List all systemd services to identify suspicious ones:
   ```
   systemctl list-units --type=service --all
   ```
3. Check the status of the suspicious service to gather more information:
   ```
   systemctl status <service_name>
   ```
4. The hidden flag is the name of the suspicious service.

**Hint 1:**
Look for services with unusual names or descriptions that don't match typical system services.

**Hint 2:**
Use `systemctl list-unit-files --type=service` to see all installed services, including inactive ones.

**Hint 3:**
Check the service status with `systemctl status <service_name>` to see when it was last activated and its description.

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From bot1, examine the suspicious service identified in the previous task.
2. View the service configuration to find the port it listens on:
   ```
   systemctl cat <service_name>
   ```
3. Look for the `ExecStart` line in the service configuration, which contains the script path.
4. Examine the script to find the port number used for communication:
   ```
   cat /usr/local/lib/.botcache/beacon.sh
   ```
5. The hidden flag is the port number used for communication.

**Hint 1:**
The service configuration file contains important information about how the service is started.

**Hint 2:**
The script launched by the service contains the port number used for communication.

**Hint 3:**
Look for the `ExecStart` line in the service configuration to find the script path.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that the suspicious service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. From bot1, list all systemd timers to identify the one associated with the suspicious service:
   ```
   systemctl list-timers --all
   ```
2. Examine the timer configuration to understand its scheduling behavior:
   ```
   systemctl cat <timer_name>
   ```
3. The hidden flag is the name of the timer responsible for scheduling the suspicious service.

**Hint 1:**
Timers are systemd components that control when services are started.

**Hint 2:**
Use `systemctl list-unit-files --type=timer` to see all installed timers.

**Hint 3:**
The timer configuration file contains information about when and how often the associated service is started.

---