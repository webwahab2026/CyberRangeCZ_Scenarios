### INFO_LEVEL

**Scenario Title:** Sandworm Intrusion Set Investigation

**Objective:**
You are an incident responder tasked with investigating a compromised system that has been targeted by the Sandworm intrusion set. The system is running a P.A.S. webshell, a type of backdoor that allows attackers to execute commands, manipulate files, and perform network activities. Your goal is to identify and mitigate the malicious activities associated with this backdoor.

**Background:**
The compromised system is part of a network that includes a command and control (C2) server, a target system, and a next-target system. The P.A.S. webshell has been used to establish persistent access and facilitate lateral movement within the network. Your task is to investigate the compromised system, identify the malicious activities, and apply appropriate containment measures.

### ACCESS_LEVEL

**Entry Host:**
- **Hostname:** target
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**Network Topology:**
- **C2 Server:** 192.168.40.5
- **Target System:** 192.168.50.5
- **Next-Target System:** 192.168.50.6

**Tools Available:**
- Standard Linux command-line tools
- Systemd service management tools
- Network diagnostic tools (e.g., ss, tcpdump)
- File inspection tools (e.g., ls, cat, find)

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay particular attention to services that are not part of the standard system configuration.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the service responsible for the suspicious activity:**
   The service name is `bkd.service`.

**Hidden Flag:**
`bkd.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of suspicious services.
4. Use `systemctl cat <service_name>` to inspect the service configuration.

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **List all network listeners:**
   ```bash
   ss -tulnp
   ```
2. **Identify the port associated with the suspicious service:**
   Look for ports that are not part of the standard system configuration.
3. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
4. **Identify the network port associated with the suspicious activity:**
   The network port is `4444`.

**Hidden Flag:**
`4444`

**Hints:**
1. Use `ss -tulnp` to list all network listeners.
2. Look for ports that are not part of the standard system configuration.
3. Use `systemctl cat <service_name>` to inspect the service configuration.
4. Identify the port associated with the suspicious service.

### TRAINING_LEVEL 3

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. **List all services:**
   ```bash
   systemctl list-units --type=service --all
   ```
2. **Identify suspicious services:**
   Look for services with unusual names or descriptions. Pay particular attention to services that are not part of the standard system configuration.
3. **Check the status of suspicious services:**
   ```bash
   systemctl status <service_name>
   ```
4. **Inspect the service configuration:**
   ```bash
   systemctl cat <service_name>
   ```
5. **Identify the service responsible for the suspicious activity:**
   The service name is `local-inventory.service`.

**Hidden Flag:**
`local-inventory.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl status <service_name>` to check the status of suspicious services.
4. Use `systemctl cat <service_name>` to inspect the service configuration.