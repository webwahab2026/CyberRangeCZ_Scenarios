Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host that appears to be infected with the Sofacy Fysbis backdoor. Your goal is to identify and analyze the malicious activity, then contain and remediate the threat.

**Scenario Learning Objectives:**
- Identify suspicious services and their behavior
- Analyze network communication patterns
- Investigate persistence mechanisms
- Contain and remediate the threat

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
- Ability to escalate to root using sudo

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
3. Look for services with unusual names or descriptions. Pay attention to services that might be related to network communication.
4. Identify the suspicious service named "systemkernelservicedefender".

**Hint 1:**
Use this command to list all services, including inactive ones:
```
systemctl list-units --type=service --all
```

**Hint 2:**
Look for services with unusual names or descriptions that might indicate malicious activity.

**Hint 3:**
Pay attention to services that might be related to network communication, as the backdoor is known to establish C2 communication.

---

**TRAINING_LEVEL**
**Task 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Examine the suspicious service identified in Task 1:
   ```
   systemctl cat systemkernelservicedefender
   ```
2. Look for the ExecStart parameter in the service definition to identify the port number used for communication.
3. Alternatively, use the following command to list listening ports and associated processes:
   ```
   ss -tulnp
   ```
4. Identify the port number 80 as the one associated with the suspicious service.

**Hint 1:**
Use this command to examine the suspicious service:
```
systemctl cat systemkernelservicedefender
```

**Hint 2:**
Look for the ExecStart parameter in the service definition to identify the port number used for communication.

**Hint 3:**
Alternatively, use this command to list listening ports and associated processes:
```
ss -tulnp
```

---

**TRAINING_LEVEL**
**Task 3: Persistence Discovery for Data Collection Service**

**Task Description:**
Investigators suspect that unauthorized activity automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. List all timers to identify the component responsible for scheduling the unauthorized activity:
   ```
   systemctl list-timers --all
   ```
2. Look for timers associated with the suspicious service identified in Task 1.
3. Identify the timer named "lab-checkin.timer" as the component responsible for scheduling the activity.
4. Examine the timer to understand its schedule and behavior:
   ```
   systemctl cat lab-checkin.timer
   ```

**Hint 1:**
Use this command to list all timers:
```
systemctl list-timers --all
```

**Hint 2:**
Look for timers associated with the suspicious service identified in Task 1.

**Hint 3:**
Examine the timer to understand its schedule and behavior using this command:
```
systemctl cat lab-checkin.timer
```

---

This scenario is designed to be deployed in the KYPO/CyberRangeCZ platform and aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks follow a logical progression and are consistent with the Intermediate difficulty level. The scenario focuses on investigating the Sofacy Fysbis backdoor, identifying its communication patterns, and analyzing its persistence mechanisms.