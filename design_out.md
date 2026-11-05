### INFO_LEVEL
**Scenario Title:** BiBi-Linux Wiper Incident Response

**Scenario Description:**
Security monitoring has detected unusual activity on the workstation host within your network. Initial analysis suggests the presence of the BiBi-Linux Wiper malware, a Linux-based wiper malware used by pro-Hamas hacktivists to target Israeli entities. Your task is to investigate the compromised workstation, identify the malware's activities, and take appropriate measures to contain and remediate the threat.

**Learning Objectives:**
1. Investigate and identify running services and their behaviors.
2. Analyze network communication to detect unauthorized activities.
3. Discover and remove persistence mechanisms.
4. Investigate lateral movement and unauthorized file transfers.
5. Identify the initial compromise vector and remediate the system.

### ACCESS_LEVEL
**Entry Host:** workstation
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH
**Privilege Boundaries:** User-level access with sudo privileges

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity that enumerated, zeroed, and renamed the company files on the workstation.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that might be related to disk maintenance or storage cleanup.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the service responsible for the suspicious activity:**
   The service name is `bibi-linux.service`.

**Hidden Flag:** `bibi-linux.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions related to disk maintenance.
3. Use `systemctl status <service_name>` to check the status of suspicious services.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the service configuration:**
   ```bash
   systemctl cat bibi-linux.service
   ```
2. **Identify the ExecStart command:**
   Look for the path to the script launched by the service.
3. **Inspect the script:**
   ```bash
   cat /usr/local/sbin/disk-maintenance
   ```
4. **Identify the network port:**
   The port number is `4444`.

**Hidden Flag:** `4444`

**Hints:**
1. Use `systemctl cat bibi-linux.service` to inspect the service configuration.
2. Look for the ExecStart command and the path to the script.
3. Use `cat /usr/local/sbin/disk-maintenance` to inspect the script and identify the network port.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the `bibi-linux.service` running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify the timer associated with the service:**
   Look for timers with names related to `bibi-linux.service`.
3. **Inspect the timer configuration:**
   ```bash
   systemctl cat bibi-linux.timer
   ```
4. **Identify the timer responsible for the persistence:**
   The timer name is `bibi-linux.timer`.

**Hidden Flag:** `bibi-linux.timer`

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with names related to `bibi-linux.service`.
3. Use `systemctl cat bibi-linux.timer` to inspect the timer configuration.