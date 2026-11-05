Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to the Umbreon rootkit compromise.

### INFO_LEVEL
**Scenario Title:** Umbreon Rootkit Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on the victim host. Your task is to investigate the compromise, identify the rootkit's behavior, and contain the threat.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities
- Investigate network communication and lateral movement
- Discover persistence mechanisms
- Identify hidden privileged user accounts
- Investigate initial compromise vectors

### ACCESS_LEVEL
**Entry Host:** victim (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity that periodically sends beacon to the attacker.

**Step-by-Step Solution:**
1. List all services on the victim host:
   ```
   systemctl list-units --type=service --all
   ```
2. Identify the suspicious service by looking for unfamiliar service names or misspellings of legitimate services. Pay attention to services with unusual descriptions or startup behavior.
3. The suspicious service is named "espeon-shell.service".

**Hint 1:**
Use the following command to list all services, including inactive ones:
```
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services with unusual names or descriptions that might indicate malicious activity.

**Hint 3:**
The suspicious service is related to a beaconing activity.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Inspect the suspicious service identified in TRAINING_LEVEL 1:
   ```
   systemctl cat espeon-shell.service
   ```
2. Look for the ExecStart parameter, which specifies the path to the script launched by the beacon service.
3. The script contains the port number to establish communication with the attacker.

**Hint 1:**
Use the following command to inspect the service configuration:
```
systemctl cat espeon-shell.service
```

**Hint 2:**
Look for the ExecStart parameter in the service configuration.

**Hint 3:**
The port number is specified in the script launched by the beacon service.

### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the beaconing service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. Check the status of the suspicious service:
   ```
   systemctl status espeon-shell.service
   ```
2. Look for any related timers or cron jobs that might be responsible for the service's persistence.
3. The cron job responsible for the service's persistence is located at "/etc/cron.d/dbus-cleanup".

**Hint 1:**
Use the following command to check the status of the suspicious service:
```
systemctl status espeon-shell.service
```

**Hint 2:**
Look for any related timers or cron jobs that might be responsible for the service's persistence.

**Hint 3:**
The cron job is located in the "/etc/cron.d/" directory.

This scenario provides a structured approach to investigating and responding to the Umbreon rootkit compromise, aligning with the provided MISP event, security profile, and sandbox environment. The tasks are designed to guide students through the investigation process while adhering to the constraints and requirements outlined.