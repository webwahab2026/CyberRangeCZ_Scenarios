### INFO_LEVEL
**Scenario Title:** Tsunami/Kaiten Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on the target system, potentially indicating a compromise by the Tsunami/Kaiten backdoor. Your task is to investigate the compromised host, identify the malicious components, and contain the threat.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities.
- Investigate network connections and discover unauthorized communication.
- Identify and disable persistence mechanisms.
- Terminate malicious processes and remove artifacts.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@target
   ```
2. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
3. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system services.
4. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
5. **Identify the service responsible for suspicious activity:**
   The service name is the hidden flag.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of suspicious services.

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@target
   ```
2. **List all listening ports:**
   ```bash
   ss -tulnp
   ```
3. **Identify the port associated with the suspicious service:**
   Look for ports that are not part of the standard system services.
4. **Check the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the network port associated with the suspicious activity:**
   The port number is the hidden flag.

**Hints:**
1. Use `ss -tulnp` to list all listening ports.
2. Look for ports that are not part of the standard system services.
3. Use `systemctl cat <service_name>` to check the service configuration.

### TRAINING_LEVEL 3
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@target
   ```
2. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
3. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system services.
4. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
5. **Identify the service responsible for collecting system information:**
   The service name is the hidden flag.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of suspicious services.