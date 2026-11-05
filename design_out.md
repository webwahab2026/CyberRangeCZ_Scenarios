Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. Here is the scenario:

---

# Scenario: Linux.Bew Backdoor Investigation

## INFO_LEVEL

**Scenario Title:** Linux.Bew Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux host infected with the Linux.Bew backdoor. This backdoor is designed for Bitcoin mining and establishes network connections to command and control (C2) servers, performs lateral movement, and maintains persistence on the infected system. Your goal is to investigate the compromised host, identify the malicious activities, and contain the threat.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd services and timers to discover persistence mechanisms.
- Analyze network connections to identify unauthorized communication.
- Contain the threat by terminating malicious processes and disabling persistence mechanisms.

**Prerequisites:**
- Basic knowledge of Linux commands and system administration.
- Familiarity with systemd and network services.
- Understanding of incident response and threat containment.

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Scenario Duration:** 60 minutes

**Target Audience:**
- Incident responders
- Security analysts
- System administrators

**Scenario Environment:**
- Compromised host: target (192.168.50.5)
- Command and control server: c2-server (192.168.40.5)
- Next target: next-target (192.168.50.6)

**Access Information:**
- Entry host: target
- Username: cyrano
- Password: cyrano

---

## ACCESS_LEVEL

**Access Instructions:**
1. Connect to the target host using SSH:
   ```
   ssh cyrano@192.168.50.5
   ```
2. Use the provided password to log in.

**Tools and Resources:**
- Linux command line tools (e.g., `systemctl`, `ss`, `ps`, `journalctl`, `iptables`)
- Text editors (e.g., `nano`, `vim`)
- Network analysis tools (e.g., `tcpdump`)

---

## TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. List all systemd services, including inactive ones:
   ```
   systemctl list-units --type=service --all
   ```
2. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or startup behavior.
3. Identify the service named `bkd.service` as the suspicious service.

**Hint 1:**
Use the `systemctl` command to list all services, including inactive ones.

**Hint 2:**
Look for services with unusual names or descriptions that do not match typical system services.

**Hint 3:**
Pay attention to services that might be related to network communication or data collection.

**Hidden Flag:**
bkd.service

---

## TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Inspect the suspicious service identified in the previous task:
   ```
   systemctl cat bkd.service
   ```
2. Look for the `ExecStart` line in the service definition, which specifies the command launched by the service.
3. Identify the port number specified as an argument to the command. In this case, the port number is `443`.

**Hint 1:**
Use the `systemctl cat` command to view the service definition.

**Hint 2:**
Look for the `ExecStart` line in the service definition, which specifies the command launched by the service.

**Hint 3:**
Identify the port number specified as an argument to the command.

**Hidden Flag:**
443

---

## TRAINING_LEVEL 3

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. List all systemd services, including timers:
   ```
   systemctl list-timers --all
   ```
2. Look for timers that might be related to data collection or system information gathering.
3. Identify the timer named `local-inventory.timer` as the suspicious timer.
4. Inspect the timer definition to confirm its purpose:
   ```
   systemctl cat local-inventory.timer
   ```

**Hint 1:**
Use the `systemctl list-timers --all` command to list all timers.

**Hint 2:**
Look for timers that might be related to data collection or system information gathering.

**Hint 3:**
Inspect the timer definition to confirm its purpose.

**Hidden Flag:**
local-inventory.timer

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. It focuses on investigating the Linux.Bew backdoor, identifying suspicious activities, and containing the threat. The scenario includes three training levels, each with a task, step-by-step solution, and hints. The hidden flags are used for automated assessment and are not revealed in the task descriptions.