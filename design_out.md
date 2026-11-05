### INFO_LEVEL

**Scenario Title:** Mirai Worm Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity originating from the internal network. Initial analysis suggests the presence of a Mirai worm variant targeting Linux-based devices. Your task is to investigate the compromised hosts, identify the malware's behavior, and contain the threat.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities.
- Investigate network communication and persistence mechanisms.
- Analyze malware behavior and containment strategies.

---

### ACCESS_LEVEL

**Entry Host:** patient-zero
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Reachable Hosts:**
- host-a (192.168.90.10)
- host-b (192.168.90.20)
- attacker (192.168.90.30)

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual CPU-intensive and network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. List all running and inactive services using the command `systemctl list-units --type=service --all`.
3. Look for unfamiliar service names or misspellings of legitimate services.
4. Identify the service named `sysnet-monitor.service` as the suspicious service.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions.

**Hint 3:**
The suspicious service is related to network monitoring.

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Inspect the suspicious service using the command `systemctl cat sysnet-monitor.service`.
3. Identify the network port specified in the `ExecStart` line of the service file.
4. The port number is `52869`.

**Hint 1:**
Use the command `systemctl cat <service>` to inspect the service file.

**Hint 2:**
Look for the `ExecStart` line in the service file.

**Hint 3:**
The port number is specified in the script path.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that a mechanism keeps the beaconing service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. List all timers using the command `systemctl list-timers --all`.
3. Identify the timer named `sysnet-monitor.timer` as the suspicious timer.
4. The timer name is `sysnet-monitor.timer`.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions.

**Hint 3:**
The suspicious timer is related to the beaconing service.

---

### TRAINING_LEVEL 4

**Task Description:**
After identifying the different activities of the malware, check how this worm dropped in the system. Identify the path of the script.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Check the bash history using the command `history`.
3. Identify the path of the script executed by the user.
4. The path of the script is `/opt/.worm/worm.sh`.

**Hint 1:**
Use the command `history` to check the bash history.

**Hint 2:**
Look for the path of the script executed by the user.

**Hint 3:**
The script is located in the `/opt/.worm` directory.

---

### TRAINING_LEVEL 5

**Task Description:**
Investigate the spread log to determine the IP addresses of the hosts that the worm has spread to.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Navigate to the worm directory using the command `cd /opt/.worm`.
3. Read the spread log using the command `cat spread.log`.
4. Identify the IP addresses of the hosts that the worm has spread to.

**Hint 1:**
Use the command `cd /opt/.worm` to navigate to the worm directory.

**Hint 2:**
Use the command `cat spread.log` to read the spread log.

**Hint 3:**
Look for the IP addresses in the spread log.

---

### TRAINING_LEVEL 6

**Task Description:**
Analyze the beacon log to determine the frequency of beaconing activity.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Navigate to the worm directory using the command `cd /opt/.worm`.
3. Read the beacon log using the command `cat beacon.log`.
4. Determine the frequency of beaconing activity by analyzing the timestamps in the log.

**Hint 1:**
Use the command `cd /opt/.worm` to navigate to the worm directory.

**Hint 2:**
Use the command `cat beacon.log` to read the beacon log.

**Hint 3:**
Look for the timestamps in the beacon log to determine the frequency of beaconing activity.

---

### TRAINING_LEVEL 7

**Task Description:**
Identify the command and control (C2) server that the worm is communicating with.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Navigate to the worm directory using the command `cd /opt/.worm`.
3. Read the worm script using the command `cat worm.sh`.
4. Identify the C2 server specified in the script.

**Hint 1:**
Use the command `cd /opt/.worm` to navigate to the worm directory.

**Hint 2:**
Use the command `cat worm.sh` to read the worm script.

**Hint 3:**
Look for the C2 server specified in the script.

---

### TRAINING_LEVEL 8

**Task Description:**
Preserve forensic evidence by creating a backup of the worm-related files.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Navigate to the worm directory using the command `cd /opt/.worm`.
3. Create a backup of the worm-related files using the command `tar -czvf worm_backup.tar.gz *`.

**Hint 1:**
Use the command `cd /opt/.worm` to navigate to the worm directory.

**Hint 2:**
Use the command `tar -czvf worm_backup.tar.gz *` to create a backup of the worm-related files.

**Hint 3:**
Ensure that the backup file is created in the current directory.

---

### TRAINING_LEVEL 9

**Task Description:**
Contain the threat by blocking unauthorized communication with the C2 server.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Block the C2 server's IP address using the command `iptables -A INPUT -s <C2_IP> -j DROP`.
3. Verify that the communication is blocked using the command `ss -tulnp`.

**Hint 1:**
Use the command `iptables -A INPUT -s <C2_IP> -j DROP` to block the C2 server's IP address.

**Hint 2:**
Replace `<C2_IP>` with the actual IP address of the C2 server.

**Hint 3:**
Use the command `ss -tulnp` to verify that the communication is blocked.

---

### TRAINING_LEVEL 10

**Task Description:**
Terminate the malicious process responsible for the beaconing activity.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Identify the process ID (PID) of the malicious process using the command `ps aux | grep worm`.
3. Terminate the malicious process using the command `kill -9 <PID>`.

**Hint 1:**
Use the command `ps aux | grep worm` to identify the process ID (PID) of the malicious process.

**Hint 2:**
Replace `<PID>` with the actual process ID of the malicious process.

**Hint 3:**
Use the command `kill -9 <PID>` to terminate the malicious process.

---

### TRAINING_LEVEL 11

**Task Description:**
Disable the persistence mechanism to prevent the malicious service from restarting.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Disable the suspicious timer using the command `systemctl stop sysnet-monitor.timer`.
3. Disable the suspicious service using the command `systemctl stop sysnet-monitor.service`.
4. Verify that the timer and service are disabled using the command `systemctl list-timers --all` and `systemctl list-units --type=service --all`.

**Hint 1:**
Use the command `systemctl stop sysnet-monitor.timer` to disable the suspicious timer.

**Hint 2:**
Use the command `systemctl stop sysnet-monitor.service` to disable the suspicious service.

**Hint 3:**
Use the command `systemctl list-timers --all` and `systemctl list-units --type=service --all` to verify that the timer and service are disabled.

---

### TRAINING_LEVEL 12

**Task Description:**
Remove confirmed malicious artifacts without destroying preserved evidence.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Navigate to the worm directory using the command `cd /opt/.worm`.
3. Remove the worm-related files using the command `rm -rf *`.
4. Verify that the files are removed using the command `ls -lah`.

**Hint 1:**
Use the command `cd /opt/.worm` to navigate to the worm directory.

**Hint 2:**
Use the command `rm -rf *` to remove the worm-related files.

**Hint 3:**
Use the command `ls -lah` to verify that the files are removed.

---

### TRAINING_LEVEL 13

**Task Description:**
Verify that malicious activity has ceased and required legitimate functionality remains operational.

**Step-by-Step Solution:**
1. SSH into the patient-zero host using the provided credentials.
2. Monitor network activity using the command `ss -tulnp`.
3. Verify that no unauthorized communication is occurring.
4. Check the system logs using the command `journalctl -xe`.

**Hint 1:**
Use the command `ss -tulnp` to monitor network activity.

**Hint 2:**
Verify that no unauthorized communication is occurring.

**Hint 3:**
Use the command `journalctl -xe` to check the system logs.

---

This scenario provides a comprehensive investigation and containment exercise for the Mirai worm variant, aligning with the provided MISP event, security profile, topology, and Ansible configuration.