### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the target system, potentially indicating the presence of the BRICKSTORM backdoor. Your task is to investigate the compromised host, identify the malicious components, and gather evidence of the backdoor's activities.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activity.
- Investigate systemd services and timers to discover unauthorized data collection and lateral movement mechanisms.
- Correlate network connections and service configurations to identify potential data exfiltration.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with systemd service management.
- Understanding of network services and ports.

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
   This command will display all services, including inactive ones.

2. **Filter for running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   This will help you identify services that are currently active.

3. **Check service details:**
   ```bash
   systemctl status updatemgr.service
   ```
   This command provides detailed information about the `updatemgr.service`, including its description, execution command, and status.

4. **Identify the suspicious service:**
   Based on the output from the previous commands, you should notice that the `updatemgr.service` has an unusual description and is responsible for the suspicious activity.

**Hidden Flag:**
The service name is `updatemgr.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for running services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Check the details of the suspicious service with `systemctl status <service>`.

---

### TRAINING_LEVEL
**Task 2: Suspicious Data Collection Service Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
   This command will display all timers, including inactive ones.

2. **Filter for active timers:**
   ```bash
   systemctl list-timers --state=active
   ```
   This will help you identify timers that are currently active.

3. **Check timer details:**
   ```bash
   systemctl cat local-inventory.timer
   ```
   This command provides detailed information about the `local-inventory.timer`, including its execution command and status.

4. **Identify the suspicious timer:**
   Based on the output from the previous commands, you should notice that the `local-inventory.timer` is responsible for the suspicious data collection activity.

**Hidden Flag:**
The timer name is `local-inventory.timer`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter for active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Check the details of the suspicious timer with `systemctl cat <timer>`.

---

### TRAINING_LEVEL
**Task 3: Suspicious File Discovery**

**Task Description:**
Investigation indicates that an unauthorized component is executing files on the compromised host. Identify the name of the script responsible for collecting system information.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will display all services, including inactive ones.

2. **Check service details:**
   ```bash
   systemctl cat local-inventory.service
   ```
   This command provides detailed information about the `local-inventory.service`, including its execution command.

3. **Identify the suspicious script:**
   Based on the output from the previous commands, you should notice that the `local-inventory.service` executes the script `/usr/local/bin/local-inventory.sh`.

**Hidden Flag:**
The filename is `/usr/local/bin/local-inventory.sh`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Check the details of the suspicious service with `systemctl cat <service>`.

**Hint 3:**
Look for the `ExecStart` line in the service details to identify the script being executed.