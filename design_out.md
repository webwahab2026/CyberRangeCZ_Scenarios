### INFO_LEVEL
**Scenario Title:** Rhombus Botnet Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity involving multiple Linux systems in your organization. Initial analysis suggests the presence of a Linux DDoS botnet known as Rhombus. Your task is to investigate the compromised hosts, identify the malicious activities, and implement appropriate containment measures.

**Learning Objectives:**
- Enumerate and analyze running services and systemd timers.
- Identify suspicious network communication and unauthorized data collection.
- Investigate persistence mechanisms and lateral movement activities.
- Implement containment measures to prevent further unauthorized communication.

---

### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Reachable Hosts:**
- bot2 (IP: 192.168.70.11)
- c2-server (IP: 192.168.70.5)

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
   The service should have a description or ExecStart command that indicates it is responsible for sending periodic beacons to the C2 server.

**Hidden Flag:** bot-beacon.service

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
   From the previous task, you should have identified the service responsible for beaconing.
2. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
3. **Look for the ExecStart command:**
   The ExecStart command should specify the path of the script launched by the service.
4. **Inspect the script:**
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
5. **Identify the network port:**
   The script should contain the network port used for communication with the C2 server.

**Hidden Flag:** 2222

**Hints:**
1. Use `systemctl cat <service_name>` to inspect the service configuration.
2. Look for the ExecStart command in the service configuration.
3. Inspect the script specified in the ExecStart command to find the network port.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify the timer associated with the suspicious service:**
   Look for timers with names related to the service identified in the previous tasks.
3. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
4. **Identify the timer responsible for scheduling the beacon service:**
   The timer should have a description or OnCalendar command that indicates it is responsible for scheduling the beacon service.

**Hidden Flag:** bot-beacon.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with names related to the suspicious service.
3. Use `systemctl cat <timer_name>` to inspect the timer configuration.