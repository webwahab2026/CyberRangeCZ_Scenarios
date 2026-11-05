### Scenario: KAITEN Botnet Investigation

**INFO_LEVEL**
The KAITEN botnet is a Linux-based malware family that spreads through Telnet scanning and establishes command-and-control (C2) connections. It performs network scanning and can be used for various malicious activities, including distributed denial-of-service (DDoS) attacks. In this scenario, you will investigate a compromised host to identify and mitigate the KAITEN botnet activity.

**ACCESS_LEVEL**
You have SSH access to the compromised host `bot1` with the username `cyrano` and password `cyrano`. You can use standard Linux commands and tools to investigate the system.

**TRAINING_LEVEL 1**
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **List all services:** Use the command `systemctl list-units --type=service --all` to list all services.
2. **Filter running services:** Use the command `systemctl list-units --type=service --state=running` to filter only the running services.
3. **Inspect suspicious services:** Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.
4. **Identify the beacon service:** The service responsible for sending beacon to the C2 server is likely to have a name or description indicating network activity or health monitoring.

**Hint 1:** Use `systemctl list-units --type=service --all` to list all services.
**Hint 2:** Filter the list to show only running services with `systemctl list-units --type=service --state=running`.
**Hint 3:** Look for services with unusual names or descriptions that might indicate network activity.

**Hidden Flag:** bot-beacon.service

**TRAINING_LEVEL 2**
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the beacon service:** Use the command `systemctl cat bot-beacon.service` to view the service configuration.
2. **Identify the ExecStart command:** Look for the `ExecStart` line in the service configuration, which specifies the path of the script launched by the service.
3. **Examine the beacon script:** Use a text editor or `cat` command to view the contents of the script specified in the `ExecStart` command.
4. **Find the communication port:** Search for the port number in the script, which is likely to be specified in a command like `nc` (netcat) or similar network utility.

**Hint 1:** Use `systemctl cat bot-beacon.service` to view the service configuration.
**Hint 2:** Look for the `ExecStart` line in the service configuration.
**Hint 3:** Examine the script specified in the `ExecStart` command to find the communication port.

**Hidden Flag:** 8080

**TRAINING_LEVEL 3**
**Task:** Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List all timers:** Use the command `systemctl list-timers --all` to list all timers.
2. **Identify the relevant timer:** Look for a timer that is associated with the `bot-beacon.service`.
3. **Inspect the timer configuration:** Use the command `systemctl cat bot-beacon.timer` to view the timer configuration.
4. **Understand the scheduling:** The timer configuration will show how often the service is scheduled to run.

**Hint 1:** Use `systemctl list-timers --all` to list all timers.
**Hint 2:** Look for a timer associated with the `bot-beacon.service`.
**Hint 3:** Use `systemctl cat bot-beacon.timer` to view the timer configuration.

**Hidden Flag:** bot-beacon.timer