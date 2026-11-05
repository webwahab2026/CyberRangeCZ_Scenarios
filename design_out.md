Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a suspected APT28 (Fancy Bear) backdoor infection on a compromised host.

---

**INFO_LEVEL**

**Scenario Title:** APT28 Backdoor Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity on the target host. Initial analysis suggests that the host may be compromised by the APT28 (Fancy Bear) backdoor. Your task is to investigate the host, identify the malicious activity, and contain the threat.

**Learning Objectives:**
- Enumerate running services and identify suspicious activity.
- Investigate network connections and discover unauthorized communication.
- Identify and disable persistence mechanisms.
- Terminate malicious processes and remove artifacts.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with incident response concepts and procedures.

**Target Audience:**
- Incident responders
- Security analysts
- System administrators

---

**ACCESS_LEVEL**

**Entry Host:** target (192.168.50.5)

**Username:** cyrano

**Password:** cyrano

**Access Method:** SSH

**Privilege Boundaries:**
- The student has sudo privileges on the entry host.
- The student can access the next-target host via SSH using the provided credentials.

---

**TRAINING_LEVEL 1**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. Connect to the target host using SSH with the provided credentials.
2. List all systemd services, including inactive ones, to identify suspicious services.
   - Command: `systemctl list-units --type=service --all`
3. Look for services with unusual names, descriptions, or startup behavior.
4. Identify the service named `bkd.service` as the suspicious service.

**Hint 1:**
Use the `systemctl` command to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual names or descriptions that do not match typical system services.

**Hint 3:**
Pay attention to services that might be related to network communication or data collection.

**Hidden Flag:** bkd.service

---

**TRAINING_LEVEL 2**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Inspect the suspicious service identified in the previous task.
   - Command: `systemctl cat bkd.service`
2. Look for the `ExecStart` line in the service definition to identify the port number.
3. The port number is specified as an argument to the `ncat` command in the `ExecStart` line.
4. Identify the port number `4444` as the network port associated with the unauthorized communication.

**Hint 1:**
Use the `systemctl cat` command to view the service definition.

**Hint 2:**
Look for the `ExecStart` line in the service definition to identify the port number.

**Hint 3:**
The port number is specified as an argument to the `ncat` command.

**Hidden Flag:** 4444

---

**TRAINING_LEVEL 3**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. List all systemd timers to identify periodically executed services.
   - Command: `systemctl list-timers --all`
2. Look for timers with unusual names or descriptions.
3. Identify the timer named `local-inventory.timer` as the suspicious timer.
4. Inspect the timer definition to confirm its association with the `local-inventory.service`.
   - Command: `systemctl cat local-inventory.timer`

**Hint 1:**
Use the `systemctl list-timers --all` command to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions.

**Hint 3:**
Inspect the timer definition to confirm its association with the suspicious service.

**Hidden Flag:** local-inventory.timer

---

This scenario is designed to be deployed on the KYPO/CyberRangeCZ platform and aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and containment of a suspected APT28 backdoor infection, with a focus on discovering hidden implementation details through investigation.