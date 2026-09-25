Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** VoIP Platform Compromise Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise of your organization's VoIP platform. Recent monitoring has detected unusual outbound network traffic from one of the VoIP servers. Your mission is to investigate this activity, identify the source of the compromise, and contain the threat.

**Scenario Objectives:**
1. Identify and investigate suspicious services and processes
2. Determine the nature of the compromise
3. Contain the threat and prevent further data exfiltration

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

**ACCESS_LEVEL**
**Entry Host:** target (192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring your VoIP platform, you noticed unusual outbound network traffic. Begin your investigation by identifying any unauthorized or suspicious services running on the target VoIP server.

**Learning Objective:** Enumerate running services and distinguish legitimate from suspicious services.

**Question:** What is the name of the suspicious service running on the target VoIP server?

**Hint:** Check running services and look for anything that doesn't belong to the standard VoIP platform services.

**Flag:** callservice

---

**TRAINING_LEVEL 2**
**Task Title:** Persistence Discovery

**Task Description:**
Now that you've identified the suspicious service, determine how it maintains persistence on the system. Investigate how this service is automatically started after system reboots.

**Learning Objective:** Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Question:** What is the name of the systemd service unit file responsible for the persistence of the suspicious service?

**Hint:** Check systemd service configurations and timers.

**Flag:** callservice.service

---

**TRAINING_LEVEL 3**
**Task Title:** C2 Communication Discovery (Port)

**Task Description:**
With the suspicious service identified, investigate its network communication patterns. Determine which network port is used for the suspicious outbound connections.

**Learning Objective:** Investigate network traffic and identify suspicious ports.

**Question:** Which network port is used by the suspicious service for its outbound communication?

**Hint:** Examine network connections and listen ports associated with the suspicious service.

**Flag:** 80

---

**Scenario Validation:**
1. The scenario is strictly aligned with the provided sandbox environment and MISP event.
2. All tasks reference real hosts, services, and file paths from the topology and Ansible data.
3. The scenario uses only indicators explicitly present in the MISP event for threat intelligence elements.
4. The scenario follows the NICE Incident Response profile, focusing on investigation, analysis, and response to network cybersecurity incidents.
5. The scenario includes exactly three TRAINING_LEVEL tasks, each with a unique focus and learning objective.

**Sandbox Analysis:**
1. Host inventory:
   - target (192.168.50.5): VoIP platform server
   - next-target (192.168.50.6): Additional server in the target network
   - c2-server (192.168.40.5): Potential command and control server

2. Service map:
   - SSH service on all hosts
   - Suspicious callservice on target
   - Systemd services and timers for various functions

3. File and artifact map:
   - /var/log/local-inventory/inventory.log
   - /etc/systemd/system/callservice.service
   - /usr/local/bin/local-inventory.sh
   - /usr/local/bin/payload-transfer.sh

4. Access model:
   - Entry via SSH to target with credentials (cyrano:cyrano)
   - SSH access to next-target from target
   - SSH access to target from next-target

5. Attack surface:
   - Investigation of running services and processes
   - Analysis of systemd service configurations
   - Examination of network connections and ports
   - Review of log files and system artifacts

This scenario provides a realistic investigation of a VoIP platform compromise, focusing on service discovery, persistence mechanisms, and C2 communication identification, all within the constraints of the provided sandbox environment and MISP event.