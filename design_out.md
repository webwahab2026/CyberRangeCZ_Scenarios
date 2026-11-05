Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a BRICKSTORM backdoor infection on a Linux system.

---

**INFO_LEVEL**

**Scenario Title:** BRICKSTORM Backdoor Investigation

**Objective:**
You are an incident responder tasked with investigating a suspected BRICKSTORM backdoor infection on a Linux system. Your goal is to identify the malicious activity, contain the threat, and remove it from the system.

**Background:**
The BRICKSTORM backdoor is a sophisticated 64-bit ELF executable written in Go. It uses advanced techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution to evade detection. The backdoor also employs DoH, nested TLS encryption, and abuses a legitimate cloud service for command and control (C2) communication.

**Access Information:**
- **Entry Host:** target (192.168.50.5)
- **Username:** cyrano
- **Password:** cyrano

---

**ACCESS_LEVEL**

**Task:**
Gain access to the target system using the provided credentials and perform an initial investigation to identify any suspicious services or processes.

**Step-by-Step Solution:**
1. SSH into the target system using the provided credentials:
   ```
   ssh cyrano@192.168.50.5
   ```
2. Once logged in, list all running services to identify any suspicious activity:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for any unfamiliar or suspicious service names, descriptions, or startup behaviors.

**Hints:**
1. Use the `systemctl` command to list all services.
2. Pay attention to services with unusual names or descriptions.
3. Check the status of suspicious services using `systemctl status <service_name>`.

---

**TRAINING_LEVEL**

**Task:** Suspicious C2 Service Discovery

**Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution to Find the Hidden Flag:**
1. List all services to identify any suspicious activity:
   ```
   systemctl list-units --type=service --all
   ```
2. Investigate the suspicious service by checking its status and configuration:
   ```
   systemctl status updatemgr.service
   systemctl cat updatemgr.service
   ```
3. Identify the service name responsible for the suspicious activity.

**Hints:**
1. Use the `systemctl` command to list all services and look for any unfamiliar or suspicious service names.
2. Check the status of the suspicious service using `systemctl status <service_name>`.
3. Inspect the service configuration using `systemctl cat <service_name>`.

---

**TRAINING_LEVEL**

**Task:** C2 Communication Discovery (Port)

**Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution to Find the Hidden Flag:**
1. List all services to identify any suspicious activity:
   ```
   systemctl list-units --type=service --all
   ```
2. Investigate the suspicious service by checking its status and configuration:
   ```
   systemctl status updatemgr.service
   systemctl cat updatemgr.service
   ```
3. Identify the network port associated with the suspicious service by examining the `ExecStart` command in the service configuration.

**Hints:**
1. Use the `systemctl` command to list all services and look for any unfamiliar or suspicious service names.
2. Check the status of the suspicious service using `systemctl status <service_name>`.
3. Inspect the service configuration using `systemctl cat <service_name>` and look for the port number in the `ExecStart` command.

---

**TRAINING_LEVEL**

**Task:** Suspicious Data Collection Service Discovery

**Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution to Find the Hidden Flag:**
1. List all services and timers to identify any suspicious activity:
   ```
   systemctl list-units --type=service --all
   systemctl list-timers --all
   ```
2. Investigate the suspicious service by checking its status, configuration, and logs:
   ```
   systemctl status local-inventory.service
   systemctl cat local-inventory.service
   journalctl -u local-inventory.service
   ```
3. Identify the service name responsible for the suspicious data collection activity.

**Hints:**
1. Use the `systemctl` command to list all services and timers and look for any unfamiliar or suspicious service names.
2. Check the status of the suspicious service using `systemctl status <service_name>`.
3. Inspect the service configuration using `systemctl cat <service_name>` and examine the logs using `journalctl -u <service_name>`.

---

This scenario provides a structured approach to investigating and responding to a BRICKSTORM backdoor infection on a Linux system. The tasks are designed to guide students through the process of identifying suspicious services, determining network ports associated with unauthorized communication, and discovering services responsible for data collection. The scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration.