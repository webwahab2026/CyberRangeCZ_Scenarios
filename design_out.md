### INFO_LEVEL
**Scenario Title:** Kinsing Cryptominer Investigation

**Scenario Description:**
Security monitoring has detected unusual CPU usage and network activity on a Linux host in your environment. Initial analysis suggests the presence of cryptocurrency mining malware. Your task is to investigate the compromised host, identify the malicious activities, and take appropriate remediation steps.

**Learning Objectives:**
1. Enumerate running services and identify suspicious activities.
2. Investigate network communication to discover unauthorized connections.
3. Analyze persistence mechanisms to understand how the malware maintains its presence.
4. Investigate lateral movement to identify how the malware spreads to other hosts.
5. Identify the initial compromise vector and remediate the infection.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with common cybersecurity tools and techniques.

---

### ACCESS_LEVEL
**Entry Host:** miner-host
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Reachable Hosts:**
- pool-server (192.168.40.5)
- second-host (192.168.50.6)

**Privilege Boundaries:**
- You have sudo privileges on the entry host.
- You can SSH to other hosts using the provided credentials.

---

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual CPU-intensive and network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Log in to the miner-host using SSH with the provided credentials.
2. List all running services using the command `systemctl list-units --type=service --state=running`.
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of the standard system services.
4. Identify the service associated with high CPU consumption by sorting processes by CPU usage using the command `ps aux --sort=-%cpu | head -20`.
5. Investigate the identified service further by checking its status and configuration using `systemctl status <service>` and `systemctl cat <service>`.

**Hint 1:**
Use the command `systemctl list-units --type=service --state=running` to list all running services.

**Hint 2:**
Sort processes by CPU usage with `ps aux --sort=-%cpu | head -20` to identify the high-CPU consumption process.

**Hint 3:**
Check the status and configuration of the suspicious service using `systemctl status <service>` and `systemctl cat <service>`.

**Hidden Flag:**
The service name responsible for the suspicious activity is `sys-monitor.service`.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From the miner-host, investigate the network listeners using the command `ss -tulnp`.
2. Identify the port associated with the suspicious service by checking the service configuration using `systemctl cat <service>`.
3. Look for the `ExecStart` line in the service configuration, which specifies the path to the script launched by the miner service.
4. Examine the script to find the port number used for communication.

**Hint 1:**
Use the command `ss -tulnp` to list all network listeners.

**Hint 2:**
Check the service configuration using `systemctl cat <service>` to find the `ExecStart` line.

**Hint 3:**
Examine the script specified in the `ExecStart` line to find the port number.

**Hidden Flag:**
The network port associated with the unauthorized communication is `80`.

---

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the miner service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. From the miner-host, check the status of the suspicious service using `systemctl status <service>`.
2. Look for any associated timers or cron jobs that might be responsible for the service's persistence.
3. Use the command `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs.
4. Examine the identified cron job or timer to understand its role in maintaining the service's persistence.

**Hint 1:**
Check the status of the suspicious service using `systemctl status <service>`.

**Hint 2:**
Search for cron jobs using `grep -Rni . /etc/cron.d/ 2>/dev/null`.

**Hint 3:**
Examine the identified cron job or timer to understand its role in maintaining the service's persistence.

**Hidden Flag:**
The cron job responsible for the miner service's persistence is located at `/etc/cron.d/sysupdate`.