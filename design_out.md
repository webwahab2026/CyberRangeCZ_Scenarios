### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target system has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromised host, identify the malicious activities, and contain the threat.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```
   ssh cyrano@192.168.50.5
   ```
2. List all services to identify the suspicious one:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. The suspicious service is likely to be named `systemkernelservicedefender.service`.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions that do not match standard system services.

**Hint 3:**
The suspicious service might have a name that includes "kernel" or "service" but is not a standard system service.

**Hidden Flag:**
systemkernelservicedefender.service

**TRAINING_LEVEL 2:**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```
   ssh cyrano@192.168.50.5
   ```
2. Check the status of the suspicious service identified in the previous task:
   ```
   systemctl status systemkernelservicedefender.service
   ```
3. Look for the port number in the service configuration. The port number is likely specified in the `ExecStart` line.
4. The port number used by the suspicious service is `80`.

**Hint 1:**
Use the command `systemctl status <service>` to check the status and configuration of the suspicious service.

**Hint 2:**
Look for the port number in the `ExecStart` line of the service configuration.

**Hint 3:**
The port number is likely to be a standard port number, such as 80 or 443.

**Hidden Flag:**
80

**TRAINING_LEVEL 3:**
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```
   ssh cyrano@192.168.50.5
   ```
2. List all timers to identify the one responsible for periodic execution of the suspicious service:
   ```
   systemctl list-timers --all
   ```
3. Look for any unfamiliar or suspicious timer names. Pay attention to timers with unusual descriptions or those that are not part of standard system timers.
4. The suspicious timer is likely to be named `lab-checkin.timer`.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions that do not match standard system timers.

**Hint 3:**
The suspicious timer might have a name that includes "checkin" or "lab".

**Hidden Flag:**
lab-checkin.timer