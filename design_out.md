### INFO_LEVEL
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that appears to be infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activity, understand the backdoor's behavior, and take appropriate containment measures.

**Learning Objectives:**
- Identify suspicious services and their associated ports.
- Analyze systemd timers and services for persistence mechanisms.
- Investigate lateral movement activities and file transfers.
- Contain the threat by terminating malicious processes and disabling persistence mechanisms.

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
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. List all services, including inactive ones:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. Identify the suspicious service name.

**Hint 1:**
Use the following command to list all services, including inactive ones:
```bash
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services with unusual names or descriptions that do not match standard system services.

**Hint 3:**
Check the status of the suspicious service to gather more information:
```bash
systemctl status <service_name>
```

**Hidden Flag:**
systemkernelservicedefender.service

---

### TRAINING_LEVEL
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. Check the status of the suspicious service identified in Task 1:
   ```bash
   systemctl status systemkernelservicedefender.service
   ```
3. Look for the port number in the ExecStart command. The port number is specified as an argument to the ncat command.
4. Verify the port is listening using the following command:
   ```bash
   ss -tulnp | grep <port_number>
   ```

**Hint 1:**
Use the following command to check the status of the suspicious service:
```bash
systemctl status systemkernelservicedefender.service
```

**Hint 2:**
Look for the port number in the ExecStart command. The port number is specified as an argument to the ncat command.

**Hint 3:**
Verify the port is listening using the following command:
```bash
ss -tulnp | grep <port_number>
```

**Hidden Flag:**
80

---

### TRAINING_LEVEL
**Task 3: Persistence Discovery for Data Collection Service**

**Task Description:**
Investigators suspect that unauthorized activity automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. List all systemd timers to identify the component responsible for scheduling the unauthorized activity:
   ```bash
   systemctl list-timers --all
   ```
3. Look for timers associated with the suspicious service identified in Task 1.
4. Check the details of the identified timer to understand its scheduling mechanism:
   ```bash
   systemctl cat <timer_name>
   ```

**Hint 1:**
Use the following command to list all systemd timers:
```bash
systemctl list-timers --all
```

**Hint 2:**
Look for timers associated with the suspicious service identified in Task 1.

**Hint 3:**
Check the details of the identified timer to understand its scheduling mechanism:
```bash
systemctl cat <timer_name>
```

**Hidden Flag:**
lab-checkin.timer