### INFO_LEVEL
**Scenario Title:** PULSEJUMP Trojan Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on the victim host. Your task is to investigate the compromised system, identify the malicious activities, and determine the extent of the compromise.

**Learning Objectives:**
- Enumerate running services to identify suspicious activities.
- Investigate systemd timers and services for persistence mechanisms.
- Analyze network communication to identify command and control (C2) activities.
- Discover initial compromise vectors and persistence mechanisms.

---

### ACCESS_LEVEL
**Entry Host:** victim
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity of periodically collecting `/etc/passwd`, home directory listings, and sensitive files, then exfiltrating them to a C2 server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   - Use `systemctl list-units --type=service --all` to list all services.
   - Look for unfamiliar or suspicious service names.

2. **Inspect Service Details:**
   - Use `systemctl cat <service>` to inspect the service configuration.
   - Pay attention to the `ExecStart` field, which specifies the script launched by the service.

3. **Identify the Suspicious Service:**
   - The service responsible for the suspicious activity is likely named `net-diag-harvest.service`.

**Hidden Flag:** net-diag-harvest.service

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl cat <service>` to inspect the service configuration.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the Suspicious Service:**
   - Use `systemctl cat net-diag-harvest.service` to inspect the service configuration.

2. **Identify the Port:**
   - The `ExecStart` field in the service configuration contains the port number used for communication.

3. **Verify the Port:**
   - Use `ss -tulnp` to verify the port is listening.

**Hidden Flag:** 5556

**Hints:**
1. Use `systemctl cat net-diag-harvest.service` to inspect the service configuration.
2. Look for the `ExecStart` field, which specifies the port number.
3. Use `ss -tulnp` to verify the port is listening.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the Credential Harvester Service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **List All Timers:**
   - Use `systemctl list-timers --all` to list all timers.

2. **Inspect Timer Details:**
   - Use `systemctl cat <timer>` to inspect the timer configuration.
   - Look for timers associated with the `net-diag-harvest.service`.

3. **Identify the Persistence Mechanism:**
   - The timer responsible for the persistence is likely named `net-diag-harvest.timer`.

**Hidden Flag:** net-diag-harvest.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the `net-diag-harvest.service`.
3. Use `systemctl cat <timer>` to inspect the timer configuration.