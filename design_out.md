Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the target system, potentially indicating the presence of the Sofacy Fysbis backdoor. Your task is to investigate this activity, identify the malicious components, and contain the threat.

**Scenario Learning Objectives:**
- Enumerate running services and identify suspicious components
- Investigate network communication and data exfiltration
- Analyze persistence mechanisms
- Implement containment measures

**Scenario Difficulty Level:** Intermediate

**Scenario Type:** Exercise

**Scenario Duration:** 60 minutes

---

**ACCESS_LEVEL**
**Entry Host:** target (192.168.50.5)
**Username:** cyrano
**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- Initial access with user-level privileges
- Escalation to root privileges may be required for certain tasks

**Reachable Hosts:**
- next-target (192.168.50.6)

---

**TRAINING_LEVEL**
**Task 1: Suspicious Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH with the provided credentials.
2. List all services, including inactive ones, to identify suspicious components:
   ```
   systemctl list-units --type=service --all
   ```
3. Filter the list to show only running services:
   ```
   systemctl list-units --type=service --state=running
   ```
4. Look for services with unusual names or descriptions that might indicate malicious activity.
5. Identify the service named "bkd.service" as the suspicious component.

**Hint 1:**
Use systemctl commands to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual names or descriptions that might indicate malicious activity.

**Hint 3:**
Focus on services that are currently running or enabled.

---

**TRAINING_LEVEL**
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Examine the suspicious service identified in Task 1:
   ```
   systemctl cat bkd.service
   ```
2. Look for the ExecStart parameter in the service definition to identify the port number.
3. Alternatively, use the ss command to list listening ports:
   ```
   ss -tulnp
   ```
4. Identify the port number 80 as the network port associated with the suspicious communication.

**Hint 1:**
Use systemctl cat to examine the service definition and look for the ExecStart parameter.

**Hint 2:**
Alternatively, use the ss command to list listening ports and identify the one associated with the suspicious service.

**Hint 3:**
Pay attention to the port number specified in the service definition or listed by the ss command.

---

**TRAINING_LEVEL**
**Task 3: Persistence Discovery for Data Collection Service**

**Task Description:**
Investigators suspect that unauthorized activity automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. List all systemd timers to identify components responsible for scheduling periodic activities:
   ```
   systemctl list-timers --all
   ```
2. Look for timers associated with the suspicious service identified in Task 1.
3. Examine the timer definition to understand its scheduling behavior:
   ```
   systemctl cat lab-checkin.timer
   ```
4. Identify the timer named "lab-checkin.timer" as the component responsible for scheduling the unauthorized activity.

**Hint 1:**
Use systemctl list-timers to identify components responsible for scheduling periodic activities.

**Hint 2:**
Look for timers associated with the suspicious service identified in Task 1.

**Hint 3:**
Examine the timer definition to understand its scheduling behavior and identify the responsible component.

---

This scenario is designed to be deployed on the KYPO/CyberRangeCZ platform and strictly aligns with the provided sandbox environment, MISP event, and security profile. The tasks are structured to guide students through the investigation process while maintaining the integrity of the sandbox and the confidentiality of the hidden flags.