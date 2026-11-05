### Scenario: Octopus-Rex Botnet Investigation

**INFO_LEVEL**
The Octopus-Rex botnet is a multi-task botnet malware developed in Go that targets Linux servers. It has been observed evolving with various features over the last seven months. The botnet is known for its command-and-control (C2) capabilities, persistence mechanisms, and ability to perform lateral movement within a network. In this scenario, you will investigate a compromised host to identify and mitigate the Octopus-Rex botnet activities.

**ACCESS_LEVEL**
- **Entry Host:** bot1
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**TRAINING_LEVEL 1**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   - Use the command `systemctl list-units --type=service --state=running` to list all running services.
   - Look for any unfamiliar or suspicious service names.

2. **Check Inactive Services:**
   - Use the command `systemctl list-units --type=service --state=inactive` to list all inactive services.
   - Look for any unfamiliar or suspicious service names.

3. **Inspect Service Details:**
   - Use the command `systemctl cat <service>` to inspect the details of the suspicious service.
   - Pay attention to the `ExecStart` field, which specifies the path of the script launched by the service.

4. **Identify the Beacon Service:**
   - The beacon service is likely to have a name that does not match common system services.
   - The service should have a description related to system health or network diagnostics.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services, both running and inactive.

**Hint 2:**
Look for services with unusual descriptions or those that do not match common system services.

**Hint 3:**
Use the command `systemctl cat <service>` to inspect the details of a suspicious service and look for the `ExecStart` field.

**Hidden Flag:**
The name of the beacon service.

**TRAINING_LEVEL 2**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the Beacon Service:**
   - From the previous task, identify the beacon service.

2. **Inspect Service Configuration:**
   - Use the command `systemctl cat <service>` to inspect the configuration of the beacon service.
   - Look for the `ExecStart` field, which specifies the path of the script launched by the service.

3. **Examine the Beacon Script:**
   - Use a text editor or `cat` command to examine the script specified in the `ExecStart` field.
   - Look for the network port used for communication with the C2 server.

4. **Verify the Port:**
   - Use the command `ss -tulnp` to verify that the identified port is being used by the beacon service.

**Hint 1:**
Use the command `systemctl cat <service>` to inspect the configuration of the beacon service.

**Hint 2:**
Look for the `ExecStart` field in the service configuration and examine the script specified.

**Hint 3:**
Use the command `ss -tulnp` to verify the network port used by the beacon service.

**Hidden Flag:**
The network port used for communication with the C2 server.

**TRAINING_LEVEL 3**
**Task Description:**
Investigators suspect that the beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. **List All Timers:**
   - Use the command `systemctl list-timers --all` to list all systemd timers.
   - Look for any unfamiliar or suspicious timer names.

2. **Inspect Timer Details:**
   - Use the command `systemctl cat <timer>` to inspect the details of the suspicious timer.
   - Pay attention to the `OnCalendar` field, which specifies the schedule for the timer.

3. **Verify Timer Status:**
   - Use the command `systemctl status <timer>` to verify the status of the timer.
   - Ensure that the timer is enabled and active.

4. **Identify the Beacon Timer:**
   - The beacon timer is likely to have a name that matches or is related to the beacon service.
   - The timer should have a schedule that matches the periodic execution of the beacon service.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all systemd timers.

**Hint 2:**
Look for timers with unusual names or those that do not match common system timers.

**Hint 3:**
Use the command `systemctl cat <timer>` to inspect the details of a suspicious timer and look for the `OnCalendar` field.

**Hidden Flag:**
The name of the timer responsible for scheduling the beacon service.