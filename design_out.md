### INFO_LEVEL
**Title:** CDRThief Investigation

**Description:**
Security monitoring has detected unusual activity on the target VoIP platform. Your task is to investigate and respond to this potential compromise involving the CDRThief malware.

**Objective:**
Identify and contain the CDRThief malware affecting the VoIP platform. Investigate the compromised host, determine the extent of the infection, and implement containment measures.

**Learning Objectives:**
- Enumerate running services and identify suspicious activities.
- Investigate network communication and data exfiltration.
- Implement containment measures to prevent further unauthorized access.

---

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Network Topology:**
- **target (192.168.50.5):** Compromised VoIP platform running Linknat VOS2009.
- **next-target (192.168.50.6):** Adjacent host in the same network segment.
- **c2-server (192.168.40.5):** Potential command and control server.

**Tools Available:**
- Standard Linux command-line tools (e.g., `ss`, `systemctl`, `journalctl`, `ps`, `find`, `iptables`).
- SSH access to investigate and contain the threat.

---

### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all running services:**
   ```bash
   systemctl list-units --type=service --state=running
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard VoIP platform.
3. **Inspect the suspicious service:**
   ```bash
   systemctl status <service_name>
   ```
   Replace `<service_name>` with the name of the suspicious service identified in the previous step.
4. **Check the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   Look for any unusual configurations or commands being executed.

**Hint 1:**
Use `systemctl list-units --type=service --all` to see all services, including inactive ones.

**Hint 2:**
Look for services with unusual descriptions or those that are not part of the standard VoIP platform.

**Hint 3:**
Use `ss -tulnp` to check for network listeners associated with the suspicious service.

---

### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Identify the suspicious service:**
   Use the information gathered from the previous task to identify the service responsible for the suspicious activity.
2. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
   Look for the `ExecStart` line, which specifies the command launched by the service.
3. **Determine the port number:**
   The port number is typically specified as an argument in the `ExecStart` command. For example, if the command is `/usr/bin/ncat -lk 80 -c "cat /var/log/local-inventory/inventory.log"`, the port number is `80`.
4. **Verify the port is listening:**
   ```bash
   ss -tulnp | grep <port_number>
   ```
   Replace `<port_number>` with the port number identified in the previous step.

**Hint 1:**
Use `systemctl status <service_name>` to check the current status and configuration of the service.

**Hint 2:**
Look for the `ExecStart` line in the service configuration to identify the port number.

**Hint 3:**
Use `ss -tulnp` to verify that the port is actively listening for connections.

---

### TRAINING_LEVEL 3
**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all systemd timers:**
   ```bash
   systemctl list-timers --all
   ```
2. **Identify suspicious timers:**
   Look for timers that are not part of the standard VoIP platform or those that execute scripts collecting system information.
3. **Inspect the suspicious timer:**
   ```bash
   systemctl cat <timer_name>
   ```
   Replace `<timer_name>` with the name of the suspicious timer identified in the previous step.
4. **Check the associated service:**
   ```bash
   systemctl cat <service_name>
   ```
   Replace `<service_name>` with the name of the service associated with the timer. Look for any unusual configurations or commands being executed.

**Hint 1:**
Use `systemctl list-unit-files --type=timer` to see all timers, including inactive ones.

**Hint 2:**
Look for timers that execute scripts collecting system information or those that are not part of the standard VoIP platform.

**Hint 3:**
Use `journalctl -u <service_name>` to check the logs of the associated service for any suspicious activity.

---