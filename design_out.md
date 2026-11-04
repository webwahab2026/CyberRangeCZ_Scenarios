Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** Linux/NyaDrop Backdoor Investigation

**INFO_LEVEL:**
Linux/NyaDrop is a backdoor and dropper malware that targets MIPS-based IoT devices. It opens an internet socket (AF_INET) to remotely connect to a remote host for receiving data of any Linux executable stream intended to infect the compromised machine. The received data is saved as 'nya' ELF malware file and then executed by Linux/NyaDrop with its permission privilege on the targeted MIPS CPU architecture device. The 'nya' dropped file will be deleted every time the next new attacks are successfully logged in to the MIPS machine and then updating the previously saved 'nya' malware.

**ACCESS_LEVEL:**
You have SSH access to the target machine with the following credentials:
- Hostname: target
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Suspicious C2 Service Discovery
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. SSH into the target machine using the provided credentials.
2. List all services using the command: `systemctl list-units --type=service --all`
3. Look for any unfamiliar or suspicious service names.
4. The suspicious service is named `nyadrop.service`.

**Hidden Flag:** nyadrop.service

**Hints:**
1. Use `systemctl` commands to list all services.
2. Look for services with unusual or unfamiliar names.
3. The suspicious service is a systemd service.

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Check the status of the suspicious service using the command: `systemctl status nyadrop.service`
2. Look for the port number in the ExecStart line of the service configuration.
3. The port number is `4444`.

**Hidden Flag:** 4444

**Hints:**
1. Use `systemctl status` to inspect the service configuration.
2. Look for the port number in the ExecStart line.
3. The port number is specified as an argument to the service command.

**TRAINING_LEVEL 3:**
**Task:** Suspicious File Discovery
Investigation indicates that an unauthorized component is executing files on the compromised host. Identify the file responsible for collecting system information.

**Solution:**
1. Inspect the service configuration using the command: `systemctl cat nyadrop.service`
2. Look for the ExecStart line to find the executed file.
3. The file responsible for collecting system information is `/usr/local/bin/local-inventory.sh`.

**Hidden Flag:** /usr/local/bin/local-inventory.sh

**Hints:**
1. Use `systemctl cat` to view the service configuration.
2. Look for the ExecStart line to find the executed file.
3. The file is located in the `/usr/local/bin` directory.

---

This scenario is strictly aligned with the provided sandbox environment, MISP event, and security profile. Each task is designed to guide students through the investigation process while adhering to the constraints and requirements outlined.