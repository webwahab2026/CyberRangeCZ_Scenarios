### Scenario: Mirai Worm Investigation

**INFO_LEVEL**
The Mirai worm is a well-known malware that targets Linux-based IoT devices. It scans for vulnerable devices, exploits them using embedded exploits, and then uses the compromised devices to launch distributed denial-of-service (DDoS) attacks. In this scenario, you will investigate a network compromised by a variant of the Mirai worm. Your goal is to identify the infected hosts, understand the malware's behavior, and contain the threat.

**ACCESS_LEVEL**
You have SSH access to the following hosts with the username `cyrano` and password `cyrano`:
- **patient-zero** (192.168.90.5)
- **host-a** (192.168.90.10)
- **host-b** (192.168.90.20)
- **attacker** (192.168.90.30)

You have sudo privileges on the **attacker** host.

---

### TRAINING_LEVEL 1

**Task Description**
Security monitoring has detected an unusual CPU-intensive and network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution**
1. SSH into the **patient-zero** host using the provided credentials.
2. List all running and inactive services using the command `systemctl list-units --type=service --all`.
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or startup behavior.
4. Identify the service responsible for the suspicious activity.

**Hint 1**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2**
Look for services with unusual names or descriptions that do not match typical system services.

**Hint 3**
Check the status of suspicious services using `systemctl status <service_name>`.

---

### TRAINING_LEVEL 2

**Task Description**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution**
1. SSH into the **patient-zero** host using the provided credentials.
2. Inspect the suspicious service identified in TRAINING_LEVEL 1 using the command `systemctl cat <service_name>`.
3. Look for the network port specified in the service configuration, typically in the `ExecStart` line.
4. Verify the port by checking the service status with `systemctl status <service_name>`.

**Hint 1**
Use the command `systemctl cat <service_name>` to view the service configuration.

**Hint 2**
Look for the `ExecStart` line in the service configuration to find the port number.

**Hint 3**
Verify the port by checking the service status with `systemctl status <service_name>`.

---

### TRAINING_LEVEL 3

**Task Description**
Investigators suspect that a mechanism keeps the beaconing service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution**
1. SSH into the **patient-zero** host using the provided credentials.
2. List all timers using the command `systemctl list-timers --all`.
3. Identify the timer associated with the suspicious service by checking the `WantedBy` field in the timer configuration.
4. Verify the timer's status with `systemctl status <timer_name>`.

**Hint 1**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2**
Look for timers with unusual names or descriptions that match the suspicious service.

**Hint 3**
Verify the timer's status with `systemctl status <timer_name>`.

---

This scenario provides a structured approach to investigating and containing a Mirai worm infection. Each task builds on the previous one, guiding you through the process of identifying and mitigating the threat.