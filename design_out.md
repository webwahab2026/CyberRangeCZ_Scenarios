### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on the target system, potentially indicating a compromise by the BRICKSTORM backdoor. Your task is to investigate the compromised host, identify the malicious activities, and gather evidence to understand the extent of the intrusion.

**Learning Objectives:**
- Enumerate running services to identify suspicious activities.
- Investigate network communication to discover unauthorized connections.
- Analyze systemd services and timers to uncover persistence mechanisms.
- Identify and analyze suspicious files and scripts.
- Investigate lateral movement activities.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with systemd services and network analysis tools.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL
**Task 1: Suspicious C2 Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will list all services, including inactive ones.

2. **Filter running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This command will show only the services that are currently running.

3. **Inspect the suspicious service:**
   Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that you do not recognize as part of the standard system configuration.

4. **Identify the suspicious service:**
   Based on the list of running services, identify the service that appears to be responsible for the suspicious activity. This service is likely the one that stands out as unusual or unfamiliar.

**Hidden Flag:**
The hidden flag is the name of the suspicious service. For example, if the suspicious service is named `updatemgr.service`, the hidden flag would be `updatemgr.service`.

**Hint 1:**
Use the `systemctl list-units --type=service --all` command to list all services, including inactive ones.

**Hint 2:**
Filter the list of services to show only the running services using the `systemctl list-units --type=service --state=running` command.

**Hint 3:**
Look for any unfamiliar or suspicious service names in the list of running services.

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the suspicious service:**
   ```bash
   systemctl cat updatemgr.service
   ```
   This command will display the configuration details of the `updatemgr.service`.

2. **Check the service status:**
   ```bash
   systemctl status updatemgr.service
   ```
   This command will show the current status and any recent logs associated with the service.

3. **Identify the port:**
   Look for the `ExecStart` line in the service configuration. This line specifies the command launched by the service and includes the port number as an argument.

4. **Verify the port:**
   Use the `ss -tulnp` command to list all listening ports and verify that the identified port is indeed being used by the suspicious service.

**Hidden Flag:**
The hidden flag is the port number associated with the suspicious service. For example, if the port number is `443`, the hidden flag would be `443`.

**Hint 1:**
Use the `systemctl cat updatemgr.service` command to inspect the configuration details of the suspicious service.

**Hint 2:**
Check the service status using the `systemctl status updatemgr.service` command to see any recent logs.

**Hint 3:**
Look for the `ExecStart` line in the service configuration to identify the port number.

---

### TRAINING_LEVEL
**Task 3: Suspicious Data Collection Service Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will list all timers, including inactive ones.

2. **Filter active timers:**
   ```bash
   systemctl list-timers --state=active
   ```
   This command will show only the timers that are currently active.

3. **Inspect the suspicious timer:**
   Look for any unfamiliar or suspicious timer names. Pay attention to timers with unusual descriptions or those that you do not recognize as part of the standard system configuration.

4. **Identify the suspicious timer:**
   Based on the list of active timers, identify the timer that appears to be responsible for the suspicious data collection activity. This timer is likely the one that stands out as unusual or unfamiliar.

**Hidden Flag:**
The hidden flag is the name of the suspicious timer. For example, if the suspicious timer is named `local-inventory.timer`, the hidden flag would be `local-inventory.timer`.

**Hint 1:**
Use the `systemctl list-timers --all` command to list all timers, including inactive ones.

**Hint 2:**
Filter the list of timers to show only the active timers using the `systemctl list-timers --state=active` command.

**Hint 3:**
Look for any unfamiliar or suspicious timer names in the list of active timers.