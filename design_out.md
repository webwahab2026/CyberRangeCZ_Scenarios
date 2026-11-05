### Scenario: CrossRAT Investigation and Containment

**INFO_LEVEL:**
CrossRAT is a newly discovered desktop surveillanceware tool capable of targeting Windows, OSX, and Linux systems. It is designed for remote access and control, allowing attackers to exfiltrate data and maintain persistence on infected systems. Security monitoring has detected unusual network activity on the target host, suggesting potential CrossRAT infection. Your task is to investigate, contain, and remediate the threat.

**ACCESS_LEVEL:**
- Entry Host: target (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. SSH into the target host using the provided credentials.
2. List all services to identify the suspicious one.
   - Command: `systemctl list-units --type=service --all`
3. Look for services with unusual names or descriptions.
4. Identify the service named `bkd.service` as the suspicious one.

**Hint 1:**
Use `systemctl` to list all services and look for any that seem out of place.

**Hint 2:**
Check the service descriptions for any that mention unusual or suspicious behavior.

**Hint 3:**
Look for services that are not part of the standard system services.

**Hidden Flag:**
bkd.service

**TRAINING_LEVEL 2:**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. SSH into the target host using the provided credentials.
2. Inspect the suspicious service to find the port it is listening on.
   - Command: `systemctl cat bkd.service`
3. Look for the `ExecStart` line in the service file to identify the port.
4. Identify the port number `2223` as the one used for suspicious communication.

**Hint 1:**
Use `systemctl cat` to view the service configuration file.

**Hint 2:**
Look for the `ExecStart` line in the service file to find the port number.

**Hint 3:**
The port number is specified as an argument in the `ExecStart` command.

**Hidden Flag:**
2223

**TRAINING_LEVEL 3:**
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. SSH into the target host using the provided credentials.
2. List all timers to identify the one responsible for periodic execution.
   - Command: `systemctl list-timers --all`
3. Look for timers with unusual names or descriptions.
4. Identify the timer named `local-inventory.timer` as the suspicious one.

**Hint 1:**
Use `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions.

**Hint 3:**
The timer responsible for periodic execution will have a name related to inventory or data collection.

**Hidden Flag:**
local-inventory.timer