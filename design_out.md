### Scenario: WHIRLPOOL Malware Investigation

#### INFO_LEVEL
The Barracuda Email Security Gateway (ESG) device in your network has been compromised by the WHIRLPOOL malware, specifically the Linux/WhirlPool.A variant. This malware is known to establish a reverse shell, allowing unauthorized access to the system. Your task is to investigate the compromised host, identify the malicious activities, and take appropriate measures to contain and remediate the threat.

#### ACCESS_LEVEL
You have SSH access to the compromised host `target` with the username `cyrano` and password `cyrano`. You can use standard Linux commands and tools to investigate the system.

#### TRAINING_LEVEL 1
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@target
   ```
2. List all services to identify the suspicious one:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for any unfamiliar or suspicious service names. Pay attention to services that might be related to network communication or data collection.
4. The hidden flag is the name of the suspicious service.

**Hints:**
1. Use `systemctl list-units --type=service --state=running` to list only running services.
2. Check the service descriptions for any unusual or unfamiliar entries.
3. Look for services that might be related to network communication or data collection.

#### TRAINING_LEVEL 2
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Identify the suspicious service from the previous task.
2. Inspect the service configuration to find the port it is using:
   ```bash
   systemctl cat <service>
   ```
3. Look for the `ExecStart` line in the service configuration, which specifies the command launched by the service with a port number as an argument.
4. The hidden flag is the port number used by the suspicious service.

**Hints:**
1. Use `systemctl status <service>` to check the status and configuration of the service.
2. Look for the `ExecStart` line in the service configuration to find the port number.
3. Use `ss -tulnp` to list all listening ports and identify the one used by the suspicious service.

#### TRAINING_LEVEL 3
**Task:** System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Solution:**
1. List all services, including timers, to identify the one responsible for data collection:
   ```bash
   systemctl list-timers --all
   ```
2. Look for any unfamiliar or suspicious timers that might be related to data collection.
3. Inspect the timer configuration to understand its behavior:
   ```bash
   systemctl cat <timer>
   ```
4. The hidden flag is the name of the suspicious timer.

**Hints:**
1. Use `systemctl list-unit-files --type=timer` to list all timers.
2. Check the timer configuration for any unusual or unfamiliar entries.
3. Look for timers that might be related to data collection or system information gathering.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is structured to guide the student through the investigation process while ensuring that the solution is consistent with the sandbox environment.