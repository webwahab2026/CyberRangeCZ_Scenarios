### INFO_LEVEL

**Scenario Title:** Remaiten Botnet Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity originating from several IoT devices within your network. Initial analysis suggests the presence of the Remaiten botnet malware, which targets routers and other IoT devices. Your task is to investigate the compromised hosts, identify the malicious activities, and implement appropriate containment measures.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service activation and scheduling to identify persistence mechanisms.
- Correlate network connections and service behavior to identify unauthorized communication.
- Apply targeted firewall controls to contain the threat.
- Terminate malicious processes and disable persistence mechanisms.
- Remove malicious artifacts while preserving forensic evidence.

---

### ACCESS_LEVEL

**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

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
   Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system services.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Identify the service responsible for beaconing:**
   Look for services that have network-related descriptions or are configured to run periodically.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions that indicate network activity.

**Hint 3:**
Use `systemctl status <service_name>` to check the status and configuration of suspicious services.

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
   Look for the `c2_port` variable or similar indicators.

**Hint 1:**
Use `systemctl cat <service_name>` to inspect the service configuration.

**Hint 2:**
Look for the ExecStart directive in the service configuration.

**Hint 3:**
Inspect the script specified in the ExecStart directive to find the communication port.

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
   Look for timers with names related to the service identified in TRAINING_LEVEL 1.
3. **Inspect the timer configuration:**
   ```bash
   systemctl cat <timer_name>
   ```
4. **Verify the timer's schedule and associated service:**
   Look for the `OnCalendar` directive and the `Unit` directive that specifies the associated service.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with names related to the suspicious service.

**Hint 3:**
Use `systemctl cat <timer_name>` to inspect the timer configuration and verify the associated service.

---