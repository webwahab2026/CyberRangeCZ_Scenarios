### Scenario: Earth Lusca Incident Response

**INFO_LEVEL:**
The Earth Lusca malware family, specifically the KTLVdoor backdoor, has been detected in your network. This backdoor is known for its multiplatform intrusion capabilities, including command and control (C2) communication, lateral movement, exfiltration, and persistence mechanisms. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have access to the following hosts:
- **target**: IP 192.168.50.5, username: cyrano, password: cyrano
- **next-target**: IP 192.168.50.6, username: cyrano, password: cyrano

You can use SSH to access these hosts. Start your investigation from the **target** host.

---

**TRAINING_LEVEL 1:**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@192.168.50.5
   ```
2. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
3. **Identify the suspicious service:**
   Look for a service that is not commonly associated with standard system operations. Pay attention to services with unusual names or descriptions.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services that are not part of the standard system operations.

**Hint 3:**
Check the service descriptions for any unusual or unfamiliar entries.

---

**TRAINING_LEVEL 2:**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@192.168.50.5
   ```
2. **Identify the suspicious service:**
   ```bash
   systemctl list-units --type=service --all
   ```
3. **Check the service details:**
   ```bash
   systemctl cat <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service identified in the previous step.
4. **Identify the port:**
   Look for the `ExecStart` line in the service details, which specifies the command launched by the service. The port number is typically an argument to this command.

**Hint 1:**
Use the command `systemctl cat <service_name>` to view the service details.

**Hint 2:**
Look for the `ExecStart` line in the service details.

**Hint 3:**
The port number is typically an argument to the command specified in the `ExecStart` line.

---

**TRAINING_LEVEL 3:**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **Access the target host:**
   ```bash
   ssh cyrano@192.168.50.5
   ```
2. **List all timers:**
   ```bash
   systemctl list-timers --all
   ```
3. **Identify the suspicious timer:**
   Look for a timer that is not commonly associated with standard system operations. Pay attention to timers with unusual names or descriptions.
4. **Check the timer details:**
   ```bash
   systemctl cat <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer identified in the previous step.
5. **Identify the associated service:**
   The timer details will specify the service that is triggered by the timer.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers that are not part of the standard system operations.

**Hint 3:**
Check the timer details using `systemctl cat <timer_name>` to identify the associated service.