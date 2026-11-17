Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that may be infected with the Sofacy Fysbis backdoor. Your goal is to identify and contain the malicious activity while preserving evidence for further analysis.

**Scenario Learning Objectives:**
- Enumerate running services to identify suspicious activity
- Investigate systemd services and timers for persistence mechanisms
- Analyze network connections for unauthorized communication
- Identify and contain malicious components

**Scenario Prerequisites:**
- Basic Linux command line knowledge
- Familiarity with systemd service management
- Understanding of network security concepts

**Scenario Duration:** 60 minutes

**Scenario Difficulty:** Beginner

**Scenario Type:** Exercise

**Scenario Approach:** Defence-oriented

---

**ACCESS_LEVEL**
**Entry Host:** target (192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Access:**
- From target, you can SSH to next-target (192.168.50.6) using the same credentials

---

**TRAINING_LEVEL**
**Task 1: Suspicious C2 Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH with the provided credentials.
2. List all systemd services, including inactive ones, to identify suspicious services:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.
4. Identify the service named "bkd.service" as the suspicious component.

**Hint 1:**
Use this command to list all systemd services, including inactive ones:
```
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services with unusual names or descriptions that might indicate network communication.

**Hint 3:**
Pay attention to services that might be listening on network ports.

---

**TRAINING_LEVEL**
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Examine the suspicious service identified in Task 1 using the following command:
   ```
   systemctl cat bkd.service
   ```
2. Look for the ExecStart parameter in the service definition, which specifies the command launched by the service.
3. Identify the port number specified as an argument to the ncat command in the ExecStart parameter.
4. The port number is 80.

**Hint 1:**
Use this command to examine the suspicious service:
```
systemctl cat bkd.service
```

**Hint 2:**
Look for the ExecStart parameter in the service definition, which specifies the command launched by the service.

**Hint 3:**
Identify the port number specified as an argument to the ncat command in the ExecStart parameter.

---

**TRAINING_LEVEL**
**Task 3: Suspicious Data Collection Service Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. List all systemd timers to identify services that execute periodically:
   ```
   systemctl list-timers --all
   ```
2. Look for timers with unusual names or descriptions that might indicate data collection activity.
3. Identify the timer named "local-inventory.timer" as the suspicious component.
4. Examine the associated service using the following command:
   ```
   systemctl cat local-inventory.service
   ```
5. Verify that the service is responsible for collecting system information.

**Hint 1:**
Use this command to list all systemd timers:
```
systemctl list-timers --all
```

**Hint 2:**
Look for timers with unusual names or descriptions that might indicate data collection activity.

**Hint 3:**
Examine the associated service using the following command:
```
systemctl cat local-inventory.service
```

---

**Scenario Completion:**
Upon completing all tasks, you will have identified the suspicious C2 service, determined the communication port, and discovered the data collection service. This information will help you contain the threat and prevent further unauthorized activity.

**Scenario Assessment:**
Your performance will be assessed based on the correctness of your answers and the effectiveness of your containment actions. Ensure that you preserve evidence and validate the system state after remediation.

---

This scenario is designed to be strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigation and containment tasks relevant to the Sofacy Fysbis backdoor described in the MISP event.