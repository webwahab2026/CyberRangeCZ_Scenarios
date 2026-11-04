### Scenario: XOR.DDoS Botnet Investigation

**INFO_LEVEL**
The XOR.DDoS botnet is a Linux-based malware that forces infected hosts to participate in large Distributed Denial of Service (DDoS) attack campaigns. The malware uses SSH brute force attacks to gain root access and full control of the targeted server. The botnet consists of a command-and-control (C2) server and multiple bots that communicate with the C2 server to receive commands and participate in DDoS attacks.

**ACCESS_LEVEL**
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

Your goal is to investigate the bot1 host, identify the malicious activities, and contain the threat.

---

### TRAINING_LEVEL 1

**Task Description**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution**
1. Log in to the bot1 host using the provided credentials.
2. List all running and inactive services using the command:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or startup behavior.
4. Identify the service responsible for sending beacon periodically to the C2 Server.

**Hint 1**
Use the following command to list all services, including inactive ones:
```
systemctl list-units --type=service --all
```

**Hint 2**
Look for services with unusual names or descriptions that might indicate malicious activity.

**Hint 3**
Check the status of the suspicious service using:
```
systemctl status <service_name>
```

**Hidden Flag**
The service name responsible for sending beacon periodically to the C2 Server is `bot-beacon.service`.

---

### TRAINING_LEVEL 2

**Task Description**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution**
1. From the previous task, you have identified the suspicious service `bot-beacon.service`.
2. Inspect the service configuration using the command:
   ```
   systemctl cat bot-beacon.service
   ```
3. Look for the `ExecStart` line in the service configuration, which specifies the path of the script launched by the service.
4. Check the script to find the communication port with the C2 server.

**Hint 1**
Use the following command to inspect the service configuration:
```
systemctl cat bot-beacon.service
```

**Hint 2**
Look for the `ExecStart` line in the service configuration to find the path of the script.

**Hint 3**
Check the script to find the communication port with the C2 server.

**Hidden Flag**
The network port associated with the unauthorized communication is `2222`.

---

### TRAINING_LEVEL 3

**Task Description**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution**
1. List all timers using the command:
   ```
   systemctl list-timers --all
   ```
2. Look for any unfamiliar or suspicious timer names. Pay attention to timers with unusual descriptions or startup behavior.
3. Identify the timer responsible for scheduling the C2 beacon service.

**Hint 1**
Use the following command to list all timers:
```
systemctl list-timers --all
```

**Hint 2**
Look for timers with unusual names or descriptions that might indicate malicious activity.

**Hint 3**
Check the status of the suspicious timer using:
```
systemctl status <timer_name>
```

**Hidden Flag**
The timer name responsible for scheduling the C2 beacon service is `bot-beacon.timer`.