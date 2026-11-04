### Scenario: Gafgyt Botnet Investigation

**INFO_LEVEL**
The Gafgyt botnet, also known as BASHLITE, is a malware family that targets Internet of Things (IoT) devices and Linux-based systems. It aims to compromise and gain control of these devices, often by exploiting weak or default passwords and known vulnerabilities. Gafgyt has been around since 2014 and has evolved into multiple variants, each with its own set of features and capabilities, including conducting DDoS attacks and performing other malicious activities.

**ACCESS_LEVEL**
You have access to the following hosts:
- **c2-server**: The command-and-control server.
- **bot1**: A compromised host in the botnet.
- **bot2**: Another compromised host in the botnet.
- **victim**: A target host being attacked by the botnet.

You can access these hosts using SSH with the username `cyrano` and password `cyrano`.

---

### TRAINING_LEVEL 1

**Task Description**
Security monitoring has detected an unusual network-facing component on the compromised host `bot1`. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution**
1. **Access the Host**: SSH into `bot1` using the provided credentials.
   ```bash
   ssh cyrano@bot1
   ```
2. **List All Services**: Use the following command to list all services, including inactive ones.
   ```bash
   systemctl list-units --type=service --all
   ```
3. **Identify Suspicious Services**: Look for services with unusual names or descriptions. Pay particular attention to services that are not part of the standard system services.
4. **Check Service Status**: Use the following command to check the status of the suspicious service.
   ```bash
   systemctl status <service_name>
   ```
5. **Find the Hidden Flag**: The hidden flag is the name of the suspicious service.

**Hints**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of the suspicious service.

---

### TRAINING_LEVEL 2

**Task Description**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution**
1. **Access the Host**: SSH into `bot1` using the provided credentials.
   ```bash
   ssh cyrano@bot1
   ```
2. **Inspect the Service**: Use the following command to inspect the service configuration.
   ```bash
   systemctl cat <service_name>
   ```
3. **Identify the Port**: Look for the `ExecStart` line in the service configuration. This line specifies the path of the script launched by the service.
4. **Check the Script**: Use the following command to check the script for the communication port with the C2 server.
   ```bash
   cat /usr/local/lib/.botcache/beacon.sh
   ```
5. **Find the Hidden Flag**: The hidden flag is the port number used for communication with the C2 server.

**Hints**
1. Use `systemctl cat <service_name>` to inspect the service configuration.
2. Look for the `ExecStart` line in the service configuration.
3. Use `cat /usr/local/lib/.botcache/beacon.sh` to check the script for the communication port.

---

### TRAINING_LEVEL 3

**Task Description**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution**
1. **Access the Host**: SSH into `bot1` using the provided credentials.
   ```bash
   ssh cyrano@bot1
   ```
2. **List All Timers**: Use the following command to list all timers, including inactive ones.
   ```bash
   systemctl list-timers --all
   ```
3. **Identify Suspicious Timers**: Look for timers with unusual names or descriptions. Pay particular attention to timers that are not part of the standard system timers.
4. **Check Timer Status**: Use the following command to check the status of the suspicious timer.
   ```bash
   systemctl status <timer_name>
   ```
5. **Find the Hidden Flag**: The hidden flag is the name of the suspicious timer.

**Hints**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or descriptions.
3. Use `systemctl status <timer_name>` to check the status of the suspicious timer.

---