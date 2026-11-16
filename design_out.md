### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target system has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromised host, identify the malicious activities, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

---

### TRAINING_LEVEL 1: Suspicious C2 Service Discovery

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of standard system services.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Identify the service responsible for suspicious activity:**
   The service `systemkernelservicedefender.service` appears to be suspicious.

**Hidden Flag:**
`systemkernelservicedefender.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of suspicious services.

---

### TRAINING_LEVEL 2: C2 Communication Discovery (Port)

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **List all listening ports:**
   ```bash
   ss -tulnp
   ```
2. **Identify the port used by the suspicious service:**
   Look for ports that are not part of standard system services.
3. **Check the service configuration:**
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```
4. **Identify the port number:**
   The port number used by the suspicious service is `80`.

**Hidden Flag:**
`80`

**Hints:**
1. Use `ss -tulnp` to list all listening ports.
2. Look for ports that are not part of standard system services.
3. Use `systemctl cat <service_name>` to check the service configuration.

---

### TRAINING_LEVEL 3: Suspicious Data Collection Service Discovery

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify suspicious timers:**
   Look for timers with unusual names or descriptions.
3. **Check the timer configuration:**
   ```bash
   systemctl cat local-inventory.timer
   ```
4. **Identify the service responsible for data collection:**
   The service `local-inventory.service` appears to be responsible for data collection.

**Hidden Flag:**
`local-inventory.service`

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or descriptions.
3. Use `systemctl cat <timer_name>` to check the timer configuration.