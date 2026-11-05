### INFO_LEVEL

**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised network infected with the Mirai-Fbot botnet. Your goal is to identify and contain the malicious activities, including C2 communication, data collection, and flood attacks.

**Learning Objectives:**
- Enumerate running services to identify suspicious activities.
- Investigate systemd services and timers for persistence mechanisms.
- Analyze network connections to detect unauthorized communication.
- Contain and remediate the botnet infection.

---

### ACCESS_LEVEL

**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Reachable Hosts:**
- bot2 (192.168.70.11)
- c2-server (192.168.70.5)

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. Connect to the bot1 host using SSH:
   ```bash
   ssh cyrano@bot1
   ```
2. List all systemd services to identify suspicious activities:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar service names or misspellings of legitimate services. Pay attention to services with unusual descriptions or startup behavior.
4. Identify the service responsible for sending beacon periodically to the C2 Server. The hidden flag is the name of this service.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. The service responsible for sending beacon periodically to the C2 Server is likely to have a name related to "beacon" or "health".

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Connect to the bot1 host using SSH:
   ```bash
   ssh cyrano@bot1
   ```
2. Inspect the C2 service definition to find the communication port:
   ```bash
   systemctl cat bot-beacon.service
   ```
3. Pay particular attention to the `ExecStart` line, which specifies the path of the script launched by the service.
4. Check the script to find the communication port with the C2 server. The hidden flag is the port number.

**Hints:**
1. Use `systemctl cat <service>` to inspect the service definition.
2. Look for the `ExecStart` line in the service definition.
3. Check the script specified in the `ExecStart` line to find the communication port.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. Connect to the bot1 host using SSH:
   ```bash
   ssh cyrano@bot1
   ```
2. List all systemd timers to identify the component responsible for scheduling the C2 beacon service:
   ```bash
   systemctl list-timers --all
   ```
3. Identify the timer associated with the C2 beacon service. The hidden flag is the name of this timer.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with names related to "beacon" or "health".
3. The timer responsible for scheduling the C2 beacon service is likely to have a name similar to the service name but with a ".timer" suffix.

---