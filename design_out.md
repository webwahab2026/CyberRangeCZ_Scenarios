### INFO_LEVEL
**Scenario Title:** BiBi-Linux Wiper Incident Response

**Scenario Description:**
Security monitoring systems have detected unusual activity on the workstation host within your organization's network. Initial analysis suggests the presence of the BiBi-Linux Wiper malware, a Linux-based wiper malware used by pro-Hamas hacktivists to target Israeli entities. Your task is to investigate the incident, identify the malware's behavior, and take appropriate response actions.

**Learning Objectives:**
1. Investigate and analyze the BiBi-Linux Wiper malware's behavior.
2. Identify the malware's persistence mechanisms and lateral movement capabilities.
3. Take appropriate response actions to contain and mitigate the threat.

### ACCESS_LEVEL
**Entry Host:** workstation
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH
**Privilege Boundaries:** User-level access with sudo privileges

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual service on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity that enumerated, zeroed, and renamed the company files on the workstation.

**Step-by-Step Solution:**
1. **List all services:** Use the command `systemctl list-units --type=service --all` to list all services.
2. **Identify suspicious services:** Look for services with unusual names or descriptions. Pay attention to services that might be related to disk maintenance or storage cleanup.
3. **Check service status:** Use the command `systemctl status <service>` to check the status of the suspicious service.
4. **Inspect service configuration:** Use the command `systemctl cat <service>` to inspect the service configuration file.
5. **Identify the malicious service:** The service responsible for the suspicious activity is likely named `bibi-linux.service`.

**Hidden Flag:** bibi-linux.service

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions related to disk maintenance.
3. Use `systemctl status <service>` to check the status of the suspicious service.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect service configuration:** Use the command `systemctl cat bibi-linux.service` to inspect the service configuration file.
2. **Identify the script:** The service configuration file points to a script located at `/usr/local/sbin/disk-maintenance`.
3. **Inspect the script:** Use the command `cat /usr/local/sbin/disk-maintenance` to inspect the script.
4. **Identify the port:** The script contains a reference to a C2 server with the port number `4444`.

**Hidden Flag:** 4444

**Hints:**
1. Use `systemctl cat bibi-linux.service` to inspect the service configuration file.
2. Look for references to scripts or executables in the service configuration.
3. Use `cat /usr/local/sbin/disk-maintenance` to inspect the script and identify the port number.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the malicious service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:** Use the command `systemctl list-timers --all` to list all timers.
2. **Identify suspicious timers:** Look for timers with unusual names or descriptions related to disk maintenance.
3. **Inspect timer configuration:** Use the command `systemctl cat <timer>` to inspect the timer configuration file.
4. **Identify the malicious timer:** The timer responsible for the suspicious activity is likely named `bibi-linux.timer`.

**Hidden Flag:** bibi-linux.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or descriptions related to disk maintenance.
3. Use `systemctl cat <timer>` to inspect the timer configuration file and identify the malicious timer.