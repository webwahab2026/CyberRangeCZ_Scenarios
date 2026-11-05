### Scenario: Exaramel Backdoor Investigation

**INFO_LEVEL:**
The target system has been compromised by the Exaramel backdoor, a component of the Sandworm malware family. Exaramel is a backdoor written in Go language deployed in the Centreon directory. It ensures persistence via a scheduled task (Cron) and communicates with its command and control servers via HTTPS. Your task is to investigate the compromised system, identify the malicious activities, and contain the threat.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Log in to the target host using the provided credentials.
2. List all running and inactive services using the command: `systemctl list-units --type=service --all`
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or startup behavior.
4. Identify the service responsible for the suspicious activity.

**Hint 1:**
Use the command `systemctl list-units --type=service --state=running` to list all running services.

**Hint 2:**
Look for services with unusual names or descriptions that do not match typical system services.

**Hint 3:**
Use the command `ss -tulnp` to check for any unusual network listeners.

**Hidden Flag:**
Exaramel.service

**TRAINING_LEVEL 2:**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Log in to the target host using the provided credentials.
2. Inspect the suspicious service identified in the previous task using the command: `systemctl cat Exaramel.service`
3. Look for the port number specified in the ExecStart command.
4. Verify the port number by checking the network listeners using the command: `ss -tulnp`

**Hint 1:**
Use the command `systemctl status Exaramel.service` to check the status and configuration of the service.

**Hint 2:**
Look for the port number in the ExecStart command within the service configuration.

**Hint 3:**
Use the command `ss -tulnp` to confirm the port number is being used by the service.

**Hidden Flag:**
4444

**TRAINING_LEVEL 3:**
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. Log in to the target host using the provided credentials.
2. List all systemd services and timers using the commands: `systemctl list-units --type=service --all` and `systemctl list-timers --all`
3. Look for any services or timers that are responsible for collecting system information.
4. Identify the service or timer responsible for this activity.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers and their associated services.

**Hint 2:**
Look for services or timers with names or descriptions that indicate they are collecting system information.

**Hint 3:**
Use the command `journalctl -u <service>` to check the logs of the suspicious service.

**Hidden Flag:**
local-inventory.timer