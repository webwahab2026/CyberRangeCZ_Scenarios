### INFO_LEVEL
**Scenario Title:** Cryptocurrency Miner Investigation

**Scenario Description:**
Security monitoring has detected unusual CPU usage and network activity on a compromised host. Your task is to investigate the system, identify the malicious activity, and determine how it was deployed and spread across the network.

**Learning Objectives:**
- Enumerate running services and processes
- Investigate network connections and listeners
- Analyze systemd services and timers
- Identify persistence mechanisms
- Investigate lateral movement techniques

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
1. Connect to the miner-host using SSH with the provided credentials.
2. List all running services using the command `systemctl list-units --type=service --state=running`.
3. Identify the service with an unusual name or description.
4. Check the status of the suspicious service using `systemctl status <service>`.
5. Note the service name for the hidden flag.

**Hint 1:**
Use `systemctl list-units --type=service --state=running` to list all running services.

**Hint 2:**
Look for services with unusual names or descriptions that do not match typical system services.

**Hint 3:**
Use `systemctl status <service>` to check the status and details of a suspicious service.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From the miner-host, investigate the suspicious service identified in the previous task.
2. Use `systemctl cat <service>` to view the service configuration file.
3. Look for the `ExecStart` line, which specifies the path to the script launched by the service.
4. Inspect the script using `cat <script>` to find the port number used for communication.
5. Note the port number for the hidden flag.

**Hint 1:**
Use `systemctl cat <service>` to view the service configuration file.

**Hint 2:**
Look for the `ExecStart` line in the service configuration file to find the script path.

**Hint 3:**
Use `cat <script>` to inspect the script and find the port number used for communication.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the miner service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. From the miner-host, investigate the suspicious service identified in the previous tasks.
2. Use `systemctl status <service>` to check the status and details of the service.
3. Look for any associated timers or cron jobs that might be responsible for persistence.
4. Use `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs related to the service.
5. Note the cron job name for the hidden flag.

**Hint 1:**
Use `systemctl status <service>` to check the status and details of the service.

**Hint 2:**
Look for any associated timers or cron jobs that might be responsible for persistence.

**Hint 3:**
Use `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs related to the service.