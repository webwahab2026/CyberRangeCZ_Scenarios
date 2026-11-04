### INFO_LEVEL

**Scenario Title:** Okiru Worm Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity originating from the internal network. Initial analysis suggests the presence of the Okiru worm, a variant of the Mirai botnet malware. Your task is to investigate the compromised hosts, identify the worm's behavior, and contain the threat.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities.
- Investigate network communication and determine the command and control (C2) infrastructure.
- Analyze persistence mechanisms and contain the threat.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with network security concepts and incident response procedures.

---

### ACCESS_LEVEL

**Entry Host:** patient-zero
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Information:**
- The network is isolated, and all hosts are accessible from the entry host.
- You have administrative privileges on the entry host but limited privileges on other hosts.

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual CPU-intensive and network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **Access the Entry Host:**
   ```bash
   ssh cyrano@patient-zero
   ```

2. **List All Running Services:**
   ```bash
   systemctl list-units --type=service --all
   ```

3. **Identify Suspicious Services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system configuration.

4. **Check Service Details:**
   ```bash
   systemctl status <service_name>
   ```

5. **Identify the Suspicious Service:**
   The service responsible for the suspicious activity is likely named `sysnet-monitor.service`.

**Hidden Flag:** `sysnet-monitor.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the details of a suspicious service.

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Access the Entry Host:**
   ```bash
   ssh cyrano@patient-zero
   ```

2. **Inspect the Suspicious Service:**
   ```bash
   systemctl cat sysnet-monitor.service
   ```

3. **Identify the Port Number:**
   Look for the `ExecStart` line in the service file. The port number is specified in this line.

4. **Verify the Port:**
   ```bash
   ss -tulnp | grep <port_number>
   ```

**Hidden Flag:** `52869`

**Hints:**
1. Use `systemctl cat sysnet-monitor.service` to inspect the service file.
2. Look for the `ExecStart` line to find the port number.
3. Use `ss -tulnp | grep <port_number>` to verify the port.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that a mechanism keeps the beaconing service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **Access the Entry Host:**
   ```bash
   ssh cyrano@patient-zero
   ```

2. **List All Timers:**
   ```bash
   systemctl list-timers --all
   ```

3. **Identify the Suspicious Timer:**
   Look for timers associated with the `sysnet-monitor.service`.

4. **Inspect the Timer Details:**
   ```bash
   systemctl cat sysnet-monitor.timer
   ```

5. **Identify the Timer Name:**
   The timer responsible for the suspicious activity is likely named `sysnet-monitor.timer`.

**Hidden Flag:** `sysnet-monitor.timer`

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the `sysnet-monitor.service`.
3. Use `systemctl cat sysnet-monitor.timer` to inspect the timer details.