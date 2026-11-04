### INFO_LEVEL
**Scenario Title:** Linux.Mirai Incident Response

**Scenario Description:**
Security monitoring has detected unusual network activity on the victim host. Your task is to investigate the compromised system, identify the malware behavior, and respond to the incident.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities.
- Investigate systemd service configurations and timers.
- Analyze network communication and persistence mechanisms.
- Preserve forensic evidence and remediate the compromised system.

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
   - Look for unfamiliar service names or misspellings of legitimate services.
   - Use `systemctl status <service>` to check the status and description of each service.

2. **Identify Suspicious Service:**
   - The service responsible for the suspicious activity is likely named `dvrHelper.service`.
   - Verify the service description and ExecStart path to confirm it matches the suspicious activity.

3. **Find the Hidden Flag:**
   - The hidden flag is the name of the suspicious service: `dvrHelper.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual descriptions or startup behavior.
3. Check the ExecStart path in the service configuration to identify the suspicious activity.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the Suspicious Service:**
   - Use `systemctl cat dvrHelper.service` to view the service configuration.
   - Pay particular attention to the ExecStart line, which specifies the path to the script launched by the service.

2. **Identify the Communication Port:**
   - The script contains the port number to establish communication with the C2 server.
   - The port number is `5556`.

3. **Find the Hidden Flag:**
   - The hidden flag is the network port number: `5556`.

**Hints:**
1. Use `systemctl cat dvrHelper.service` to view the service configuration.
2. Look for the ExecStart line in the service configuration.
3. The port number is specified in the script launched by the service.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the suspicious service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **Investigate Systemd Service Activation:**
   - Use `systemctl list-timers --all` to list all timers.
   - Look for timers associated with the suspicious service.

2. **Identify the Persistence Mechanism:**
   - The timer responsible for recurring unauthorized execution of the suspicious service is named `dvrHelper.timer`.
   - Verify the timer configuration using `systemctl cat dvrHelper.timer`.

3. **Find the Hidden Flag:**
   - The hidden flag is the name of the timer: `dvrHelper.timer`.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the suspicious service.
3. Verify the timer configuration using `systemctl cat dvrHelper.timer`.