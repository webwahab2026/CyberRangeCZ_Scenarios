Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the target system, potentially indicating the presence of the Sofacy Fysbis backdoor. Your task is to investigate this activity, identify the malicious components, and implement appropriate containment measures.

**Scenario Learning Objectives:**
- Investigate suspicious services and network activity
- Identify malicious components and their behavior
- Implement containment measures to prevent further unauthorized access

**Scenario Prerequisites:**
- Familiarity with Linux command line
- Basic knowledge of systemd services
- Understanding of network security principles

**Scenario Duration:** 2 hours

**Scenario Difficulty:** Advanced

**Scenario Type:** Exercise

**Scenario Approach:** Defence-oriented

---

**ACCESS_LEVEL**
**Entry Host:** target (192.168.50.5)
**Username:** cyrano
**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- Initial access with user-level privileges
- Ability to escalate to root using sudo

**Reachable Hosts:**
- next-target (192.168.50.6)

---

**TRAINING_LEVEL**
**Task 1: Suspicious File Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the file responsible for this activity.

**Step-by-Step Solution:**
1. List all systemd services to identify suspicious components:
   ```
   systemctl list-units --type=service --all
   ```
2. Investigate the local-inventory.service, which appears to be responsible for collecting system information:
   ```
   systemctl cat local-inventory.service
   ```
3. Identify the executable file responsible for the data collection:
   ```
   systemctl show local-inventory.service -p ExecStart
   ```
4. The file /usr/local/bin/local-inventory.sh is responsible for collecting system information.

**Hint 1:**
Use systemctl commands to list and investigate services.

**Hint 2:**
Look for services with unusual names or descriptions.

**Hint 3:**
The ExecStart property of a service unit file shows the command that is executed when the service starts.

---

**TRAINING_LEVEL**
**Task 2: Data Exfiltration Detection**

**Task Description:**
Security monitoring suggests that information collected from the compromised host may be accessible to an unauthorized remote system. Investigate the available network and filesystem evidence to identify the affected data file and determine how it is exposed or transferred.

**Step-by-Step Solution:**
1. List all active network connections to identify suspicious communication:
   ```
   ss -tunap
   ```
2. Investigate the bkd.service, which appears to be responsible for network communication:
   ```
   systemctl cat bkd.service
   ```
3. Check the journal logs for the bkd.service to understand its behavior:
   ```
   journalctl -u bkd.service
   ```
4. The service is listening on port 80 and sending the contents of /var/log/local-inventory/inventory.log to connecting clients.

**Hint 1:**
Use ss command to list active network connections.

**Hint 2:**
Investigate the service responsible for the suspicious network communication.

**Hint 3:**
Check the journal logs for the service to understand its behavior.

---

**TRAINING_LEVEL**
**Task 3: C2 Containment**

**Task Description:**
Investigation has identified unauthorized communication involving the compromised host. Apply an appropriate network control to prevent further communication with the suspicious remote system while preserving legitimate network access.

**Step-by-Step Solution:**
1. Identify the IP address of the remote system communicating with the compromised host:
   ```
   journalctl -u bkd.service | grep "connected from"
   ```
2. Block the remote IP address using iptables:
   ```
   sudo iptables -I INPUT -s <remote_ip> -j DROP
   ```
3. Verify that the remote IP address is blocked:
   ```
   sudo iptables -L -n -v
   ```
4. The remote IP address <remote_ip> is now blocked, preventing further unauthorized communication.

**Hint 1:**
Use journalctl command to identify the remote IP address.

**Hint 2:**
Use iptables command to block the remote IP address.

**Hint 3:**
Verify that the remote IP address is blocked using iptables command.

---

This scenario is designed to be deployed on the KYPO/CyberRangeCZ platform and is strictly aligned with the provided sandbox environment and MISP event. The tasks are designed to be challenging and require advanced investigation skills, with a focus on defense-oriented cybersecurity approaches. The scenario includes three training level tasks, each with a step-by-step solution and hints to guide the students through the investigation process.