Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I will create a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario will focus on investigating and responding to a Kobalos malware infection.

### Scenario: Kobalos Malware Investigation and Response

#### INFO_LEVEL
The target system has been compromised by the Kobalos malware, a complex, multiplatform backdoor that targets high-performance computing (HPC) clusters and other high-profile systems. Kobalos grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. It also includes a credential stealer component that captures SSH credentials.

Your task is to investigate the compromised system, identify the malicious activities, and take appropriate containment and remediation actions.

#### ACCESS_LEVEL
- **Entry Host:** target (IP: 192.168.50.5)
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

#### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH:
   ```bash
   ssh cyrano@192.168.50.5
   ```
2. List all services, including inactive ones:
   ```bash
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. Identify the suspicious service. In this case, the service is named `sshd.service`.

**Hidden Flag:** sshd.service

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. The suspicious service is related to SSH.

#### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Check the status of the suspicious service identified in the previous task:
   ```bash
   systemctl status sshd.service
   ```
2. Look for the port number in the service configuration. You can also use the following command to list all listening ports:
   ```bash
   ss -tulnp
   ```
3. Identify the port number associated with the suspicious service. In this case, the port is `7070`.

**Hidden Flag:** 7070

**Hints:**
1. Use `systemctl status <service>` to check the service status and configuration.
2. Look for the port number in the service configuration or using `ss -tulnp`.
3. The port number is associated with the suspicious service.

#### TRAINING_LEVEL 3
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. List all timers to identify periodically executed services:
   ```bash
   systemctl list-timers --all
   ```
2. Look for timers with unusual names or descriptions. Pay attention to timers that are not part of standard system services.
3. Identify the suspicious timer. In this case, the timer is named `local-inventory.timer`.
4. Check the status of the timer to understand its behavior:
   ```bash
   systemctl status local-inventory.timer
   ```

**Hidden Flag:** local-inventory.timer

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or descriptions.
3. The suspicious timer is related to system information collection.

This scenario provides a structured approach to investigating and responding to a Kobalos malware infection, aligning with the provided MISP event, security profile, and sandbox environment. The tasks are designed to guide students through the investigation process while ensuring they discover the required information through investigation.