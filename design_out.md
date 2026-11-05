### Scenario: Supreme Backdoor Factory Investigation

**INFO_LEVEL:**
The Supreme Backdoor Factory is a set of malicious GitHub accounts and repositories used to deliver payloads. The malware creates scheduled tasks to download and execute PowerShell code from dynamic DNS subdomains. Your task is to investigate and mitigate the threat posed by this backdoor.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can investigate the system and perform necessary actions to contain and eradicate the threat.

---

### TRAINING_LEVEL 1: Suspicious C2 Service Discovery

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **Access the Target Host:**
   ```bash
   ssh cyrano@target
   ```

2. **List All Services:**
   ```bash
   systemctl list-units --type=service --all
   ```

3. **Identify Suspicious Services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of standard system services.

4. **Check Service Status:**
   ```bash
   systemctl status <service_name>
   ```

5. **Find the Hidden Flag:**
   The hidden flag is the name of the suspicious service.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of a suspicious service.

---

### TRAINING_LEVEL 2: C2 Communication Discovery (Port)

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Access the Target Host:**
   ```bash
   ssh cyrano@target
   ```

2. **List All Listening Ports:**
   ```bash
   ss -tulnp
   ```

3. **Identify the Suspicious Port:**
   Look for ports that are not part of standard system services.

4. **Check the Service Configuration:**
   ```bash
   systemctl cat <service_name>
   ```

5. **Find the Hidden Flag:**
   The hidden flag is the port number associated with the suspicious service.

**Hints:**
1. Use `ss -tulnp` to list all listening ports.
2. Look for ports that are not part of standard system services.
3. Use `systemctl cat <service_name>` to check the service configuration.

---

### TRAINING_LEVEL 3: Suspicious Data Collection Service Discovery

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **Access the Target Host:**
   ```bash
   ssh cyrano@target
   ```

2. **List All Timers:**
   ```bash
   systemctl list-timers --all
   ```

3. **Identify Suspicious Timers:**
   Look for timers with unusual names or descriptions.

4. **Check Timer Configuration:**
   ```bash
   systemctl cat <timer_name>
   ```

5. **Find the Hidden Flag:**
   The hidden flag is the name of the suspicious timer.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or descriptions.
3. Use `systemctl cat <timer_name>` to check the timer configuration.

---