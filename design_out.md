### Scenario: Sofacy Fysbis Backdoor Investigation

#### INFO_LEVEL
The target system has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromised system, identify the malicious activities, and contain the threat.

#### ACCESS_LEVEL
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

#### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
The service responsible for the suspicious activity is `systemkernelservicedefender.service`.

**Hint 1:**
Use the following command to list all services:
```bash
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services with unusual names or descriptions. The suspicious service might have a name that resembles a legitimate system service but is slightly different.

**Hint 3:**
Check the status of the suspicious service to gather more information:
```bash
systemctl status systemkernelservicedefender.service
```

#### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
The network port associated with the unauthorized communication is `80`.

**Hint 1:**
Use the following command to list all listening ports:
```bash
ss -tulnp
```

**Hint 2:**
Look for the service `systemkernelservicedefender.service` in the output and note the port it is listening on.

**Hint 3:**
Check the service configuration to confirm the port:
```bash
systemctl cat systemkernelservicedefender.service
```

#### TRAINING_LEVEL 3
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Solution:**
The service responsible for collecting system information is `local-inventory.service`.

**Hint 1:**
Use the following command to list all services:
```bash
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services that might be collecting system information, such as those with names like `inventory` or `collect`.

**Hint 3:**
Check the status of the suspicious service to gather more information:
```bash
systemctl status local-inventory.service
```

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is structured to guide the investigator through the process of identifying and containing the Sofacy Fysbis backdoor on the compromised system.