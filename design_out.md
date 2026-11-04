### Scenario: Sednit Xagent Backdoor Investigation

**INFO_LEVEL:**
The Sednit group, also known as APT29, is a sophisticated cyber espionage group believed to be operating out of Russia. They are known for targeting government agencies, diplomatic organizations, and research institutions. One of their tools of choice is the Xagent backdoor malware, which is capable of establishing persistent connections to command and control (C&C) servers, executing commands, and exfiltrating data.

In this scenario, you will investigate a compromised host that appears to be communicating with a known Sednit C&C server. Your goal is to identify the malicious activity, contain the threat, and remediate the compromised host.

**ACCESS_LEVEL:**
You have been provided with SSH access to the target host with the following credentials:
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Log in to the target host using the provided credentials.
2. List all running and inactive services using the command `systemctl list-units --type=service --all`.
3. Look for any unfamiliar or suspicious service names.
4. Identify the service responsible for the suspicious activity.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions.

**Hint 3:**
Use the command `systemctl status <service>` to check the status and details of a specific service.

**Hidden Flag:**
The name of the suspicious service.

**TRAINING_LEVEL 2:**
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From the previous task, identify the suspicious service.
2. Use the command `systemctl cat <service>` to view the service configuration file.
3. Look for the `ExecStart` line, which specifies the command launched by the service.
4. Identify the port number used by the service.

**Hint 1:**
Use the command `systemctl cat <service>` to view the service configuration.

**Hint 2:**
Look for the `ExecStart` line in the service configuration.

**Hint 3:**
The port number is usually specified as an argument to the command in the `ExecStart` line.

**Hidden Flag:**
The network port number used by the suspicious service.

**TRAINING_LEVEL 3:**
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. List all systemd services and timers using the commands `systemctl list-units --type=service --all` and `systemctl list-timers --all`.
2. Look for any suspicious or unfamiliar services or timers.
3. Investigate the suspicious service or timer by using the commands `systemctl status <service>` or `systemctl status <timer>`.
4. Identify the service or timer responsible for the unauthorized data collection.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions.

**Hint 3:**
Use the command `systemctl status <timer>` to check the status and details of a specific timer.

**Hidden Flag:**
The name of the service or timer responsible for the unauthorized data collection.