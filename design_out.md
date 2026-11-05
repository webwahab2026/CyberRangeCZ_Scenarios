### INFO_LEVEL

**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity originating from several IoT devices within your network. Initial analysis suggests the presence of the Mirai botnet, known for launching Distributed Denial of Service (DDoS) attacks. Your task is to investigate the compromised hosts, identify the malicious activities, and implement appropriate containment measures.

**Learning Objectives:**
1. Enumerate and analyze running services to identify suspicious activities.
2. Investigate network communication to uncover unauthorized C2 (Command and Control) channels.
3. Discover and disable persistence mechanisms to prevent the botnet from reactivating.
4. Implement containment measures to block further communication with the C2 server.

**Prerequisites:**
- Basic knowledge of Linux command line.
- Familiarity with systemd service management.
- Understanding of network protocols and tools like `netstat`, `ss`, and `tcpdump`.

---

### ACCESS_LEVEL

**Entry Host:**
- **Hostname:** bot1
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**Additional Hosts:**
- **Hostname:** bot2
- **Hostname:** c2-server
- **Hostname:** victim

**Network Configuration:**
- **bot1 and bot2** are on the `botnet-switch` network (192.168.70.0/24).
- **victim** is on the `victim-switch` network (192.168.80.0/24).
- **c2-server** is on the `botnet-switch` network (192.168.70.0/24).

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication or system health monitoring.
3. **Check the status of the suspicious service:**
   ```bash
   systemctl status <service_name>
   ```
4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the service responsible for beaconing:**
   The service name is the hidden flag.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions related to network communication.
3. Use `systemctl status <service_name>` to check the status of the suspicious service.

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the suspicious service:**
   Use the service name identified in TRAINING_LEVEL 1.
2. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
3. **Look for the ExecStart directive:**
   This directive specifies the path of the script launched by the service.
4. **Inspect the script to find the communication port:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
5. **Identify the port number:**
   The port number is the hidden flag.

**Hints:**
1. Use `systemctl cat <service_name>` to inspect the service configuration.
2. Look for the ExecStart directive to find the path of the script.
3. Inspect the script to find the communication port.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify the timer associated with the suspicious service:**
   Look for timers with names related to the service identified in TRAINING_LEVEL 1.
3. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
4. **Identify the timer name:**
   The timer name is the hidden flag.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with names related to the suspicious service.
3. Use `systemctl cat <timer_name>` to inspect the timer configuration.