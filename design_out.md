### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the target system, potentially indicating the presence of the Sofacy Fysbis backdoor. Your task is to investigate the compromised host, identify the malicious components, and take appropriate defensive actions.

**Learning Objectives:**
- Enumerate running services and identify suspicious components.
- Investigate network communication and data exfiltration.
- Analyze persistence mechanisms and lateral movement activities.
- Apply containment and remediation measures.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with systemd and network services.
- Understanding of basic cybersecurity principles.

---

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Network Topology:**
- **target (192.168.50.5):** Compromised host with Sofacy Fysbis backdoor.
- **next-target (192.168.50.6):** Adjacent host involved in lateral movement.
- **c2-server (192.168.40.5):** External command and control server.

**Accessible Services:**
- SSH on target and next-target.
- Systemd services and logs on target.
- Network connections and file transfers between hosts.

---

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   This command will display all services, including inactive ones.

2. **Filter for active services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
   Look for any unfamiliar or suspicious service names.

3. **Inspect the suspicious service:**
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```
   This will show the service configuration file, which includes the ExecStart command.

4. **Identify the service name:**
   The service name is `systemkernelservicedefender.service`.

**Hidden Flag:**
The hidden flag is `systemkernelservicedefender.service`.

**Hint 1:**
Use `systemctl list-units --type=service --all` to list all services, including inactive ones.

**Hint 2:**
Filter for active services using `systemctl list-units --type=service --state=running`.

**Hint 3:**
Inspect the suspicious service configuration with `systemctl cat <service>`.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the suspicious service:**
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```
   This will show the service configuration file, which includes the ExecStart command.

2. **Identify the port number:**
   The ExecStart command in the service configuration file specifies the port number as an argument. For example:
   ```bash
   ExecStart=/bin/sh -c '/usr/bin/ncat -lk 80 -c "cat /var/log/local-inventory/inventory.log" >> /var/log/lab-checkin.log 2>&1'
   ```
   The port number is `80`.

**Hidden Flag:**
The hidden flag is `80`.

**Hint 1:**
Use `systemctl cat <service>` to inspect the service configuration file.

**Hint 2:**
Look for the ExecStart command in the service configuration file.

**Hint 3:**
The port number is specified as an argument to the `ncat` command.

---

### TRAINING_LEVEL 3
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
   Look for any unfamiliar or suspicious timer names.

3. **Inspect the suspicious timer:**
   ```bash
   systemctl cat local-inventory.timer
   ```
   This will show the timer configuration file, which includes the Unit specification.

4. **Identify the service name:**
   The Unit specification in the timer configuration file points to the service responsible for the activity. For example:
   ```bash
   Unit=local-inventory.service
   ```
   The service name is `local-inventory.service`.

**Hidden Flag:**
The hidden flag is `local-inventory.service`.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers, including inactive ones.

**Hint 2:**
Filter for active timers using `systemctl list-timers --state=active`.

**Hint 3:**
Inspect the suspicious timer configuration with `systemctl cat <timer>`.