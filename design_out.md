### Scenario: Mirai Botnet Investigation

**INFO_LEVEL**
The Mirai botnet is a well-known malware family that targets Linux-based IoT devices to create a network of compromised systems, or "bots," which can be used to launch distributed denial-of-service (DDoS) attacks. The Mirai variant known as Linux/Mirai-Hilix incorporates a new TABLE encoder, which is an obfuscation or encoding technique designed to evade detection and analysis by security tools.

In this scenario, you will investigate a compromised host that is part of a Mirai botnet. Your goal is to identify and mitigate the malicious activities associated with this botnet.

**ACCESS_LEVEL**
You have SSH access to the compromised host `bot1` with the username `cyrano` and password `cyrano`. You can use this access to investigate the system and identify any suspicious activities.

---

### TRAINING_LEVEL 1

**Task Description**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution**
1. **List all services**: Use the command `systemctl list-units --type=service --all` to list all services on the system.
2. **Identify suspicious services**: Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system services.
3. **Check service status**: Use the command `systemctl status <service>` to check the status of the suspicious service. Look for services that are running or enabled.
4. **Identify the beacon service**: The service responsible for sending beacon periodically to the C2 Server is likely to have a name or description related to "beacon" or "health check."

**Hint 1**
Use the command `systemctl list-units --type=service --all` to list all services on the system.

**Hint 2**
Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system services.

**Hint 3**
Use the command `systemctl status <service>` to check the status of the suspicious service. Look for services that are running or enabled.

---

### TRAINING_LEVEL 2

**Task Description**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution**
1. **Identify the suspicious service**: From the previous task, you should have identified the service responsible for sending beacon periodically to the C2 Server.
2. **Inspect the service configuration**: Use the command `systemctl cat <service>` to inspect the service configuration file. Look for the `ExecStart` line, which specifies the path of the script launched by the service.
3. **Check the script**: Open the script specified in the `ExecStart` line and look for the network port used for communication. The port is likely specified as an argument to a network command like `nc` (netcat).
4. **Verify the port**: Use the command `ss -tulnp` to verify that the port is being used by the suspicious service.

**Hint 1**
Use the command `systemctl cat <service>` to inspect the service configuration file. Look for the `ExecStart` line.

**Hint 2**
Open the script specified in the `ExecStart` line and look for the network port used for communication.

**Hint 3**
Use the command `ss -tulnp` to verify that the port is being used by the suspicious service.

---

### TRAINING_LEVEL 3

**Task Description**
Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution**
1. **List all timers**: Use the command `systemctl list-timers --all` to list all timers on the system.
2. **Identify suspicious timers**: Look for timers with unusual names or descriptions. Pay attention to timers that are not part of the standard system timers.
3. **Inspect the timer configuration**: Use the command `systemctl cat <timer>` to inspect the timer configuration file. Look for the `OnCalendar` line, which specifies the schedule for the timer.
4. **Verify the timer**: Use the command `systemctl status <timer>` to verify that the timer is active and scheduled to run periodically.

**Hint 1**
Use the command `systemctl list-timers --all` to list all timers on the system.

**Hint 2**
Look for timers with unusual names or descriptions. Pay attention to timers that are not part of the standard system timers.

**Hint 3**
Use the command `systemctl cat <timer>` to inspect the timer configuration file. Look for the `OnCalendar` line.