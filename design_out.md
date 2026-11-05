Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. Here is the scenario:

---

# Scenario: ELF_IMEIJ Backdoor Investigation

## INFO_LEVEL

The target system has been compromised by the ELF_IMEIJ.A backdoor malware. This malware exploits CGI vulnerabilities to download and execute malicious payloads. Your task is to investigate the compromised system, identify the malicious activities, and contain the threat.

## ACCESS_LEVEL

You have SSH access to the target system with the following credentials:
- Hostname: target
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1

### Task Description
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

### Step-by-Step Solution
1. **List all services**: Use the command `systemctl list-units --type=service --all` to list all services.
2. **Filter running services**: Use the command `systemctl list-units --type=service --state=running` to filter running services.
3. **Inspect suspicious services**: Look for services with unusual names or descriptions. Pay attention to the `bkd.service` service, which appears to be suspicious.
4. **Identify the service**: The service responsible for the suspicious activity is `bkd.service`.

### Hints
1. **List all services**: Use `systemctl list-units --type=service --all` to see all services.
2. **Filter running services**: Use `systemctl list-units --type=service --state=running` to see only running services.
3. **Inspect suspicious services**: Look for services with unusual names or descriptions.

## TRAINING_LEVEL 2

### Task Description
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

### Step-by-Step Solution
1. **Inspect the service**: Use the command `systemctl cat bkd.service` to inspect the `bkd.service` service.
2. **Identify the port**: Look for the `listen_port` variable in the service file. The port number is `8080`.

### Hints
1. **Inspect the service**: Use `systemctl cat bkd.service` to see the service configuration.
2. **Identify the port**: Look for the `listen_port` variable in the service file.
3. **Check listening ports**: Use `ss -tulnp` to see listening ports and associated services.

## TRAINING_LEVEL 3

### Task Description
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

### Step-by-Step Solution
1. **List all services**: Use the command `systemctl list-units --type=service --all` to list all services.
2. **List all timers**: Use the command `systemctl list-timers --all` to list all timers.
3. **Inspect suspicious timers**: Look for timers with unusual names or descriptions. Pay attention to the `local-inventory.timer` timer, which appears to be suspicious.
4. **Identify the service**: The service responsible for collecting system information is `local-inventory.service`.

### Hints
1. **List all services**: Use `systemctl list-units --type=service --all` to see all services.
2. **List all timers**: Use `systemctl list-timers --all` to see all timers.
3. **Inspect suspicious timers**: Look for timers with unusual names or descriptions.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. It focuses on investigating and containing the ELF_IMEIJ.A backdoor malware on the target system. The tasks are structured to guide students through the investigation process while ensuring they discover the required information through investigation.