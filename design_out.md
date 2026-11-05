### INFO_LEVEL
**Scenario Title:** XMRig Cryptominer Investigation

**Scenario Description:**
Security monitoring has detected unusual CPU usage and network activity on the miner-host system. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**Learning Objectives:**
- Enumerate running services and processes
- Analyze network connections and service configurations
- Investigate persistence mechanisms
- Identify and contain malicious activity

---

### ACCESS_LEVEL
**Entry Host:** miner-host
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual CPU-intensive and network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the miner-host system using SSH with the provided credentials.
2. List all running services using the command `systemctl list-units --type=service --state=running`.
3. Identify the service with an unusual name or description. Look for services that are not part of the standard system services.
4. Check the status of the suspicious service using `systemctl status <service>`.
5. Note the service name for the hidden flag.

**Hint 1:**
Use `systemctl list-units --type=service --state=running` to list all running services.

**Hint 2:**
Look for services with unusual names or descriptions that do not match standard system services.

**Hint 3:**
Use `systemctl status <service>` to check the status and details of the suspicious service.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From the miner-host system, use `systemctl cat <service>` to inspect the service file of the suspicious service identified in TRAINING_LEVEL 1.
2. Look for the `ExecStart` line in the service file, which specifies the path to the script launched by the service.
3. Use `cat <script>` to view the contents of the script and identify the port number used for communication.
4. Note the port number for the hidden flag.

**Hint 1:**
Use `systemctl cat <service>` to inspect the service file.

**Hint 2:**
Look for the `ExecStart` line in the service file to find the script path.

**Hint 3:**
Use `cat <script>` to view the script contents and identify the port number.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the miner service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. On the miner-host system, use `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs related to the suspicious service.
2. Identify the cron job file that references the suspicious service or script.
3. Use `cat <cron-job-path>` to view the contents of the cron job file.
4. Note the path of the cron job file for the hidden flag.

**Hint 1:**
Use `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs.

**Hint 2:**
Identify the cron job file that references the suspicious service or script.

**Hint 3:**
Use `cat <cron-job-path>` to view the contents of the cron job file.