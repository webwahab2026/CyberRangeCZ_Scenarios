Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** Linux/XorDDoS Botnet Investigation

**INFO_LEVEL:**
The organization has detected unusual network activity originating from several Linux servers. Initial analysis suggests these hosts may be compromised by the Linux/XorDDoS botnet malware. Your task is to investigate these hosts, identify the malicious activity, and implement appropriate containment measures.

**ACCESS_LEVEL:**
You have SSH access to the following hosts with the username "cyrano" and password "cyrano":
- bot1 (192.168.70.10)
- bot2 (192.168.70.11)
- c2-server (192.168.70.5)

**TRAINING_LEVEL 1:**
**Task:** Security monitoring has detected an unusual network-facing component on bot1. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Solution:**
1. SSH into bot1 using the provided credentials.
2. List all services on the system using: `systemctl list-units --type=service --all`
3. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that don't match standard system services.
4. The suspicious service is named "bot-beacon.service".

**Hidden Flag:** bot-beacon.service

**Hints:**
1. Use this command to list all services: `systemctl list-units --type=service --all`
2. Look for services with unusual names or descriptions.
3. The suspicious service is related to beaconing activity.

**TRAINING_LEVEL 2:**
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system on bot1. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Examine the suspicious service found in the previous task using: `systemctl cat bot-beacon.service`
2. Look for the ExecStart parameter which specifies the path of the script launched by the service.
3. Inspect the script at `/usr/local/lib/.botcache/beacon.sh` to find the communication port with C2 server.
4. The C2 port number is 2222.

**Hidden Flag:** 2222

**Hints:**
1. Use this command to examine the service: `systemctl cat bot-beacon.service`
2. Look for the ExecStart parameter in the service file.
3. The communication port is specified in the beacon script.

**TRAINING_LEVEL 3:**
**Task:** Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically on bot1. Determine which system component is responsible for scheduling this activity.

**Solution:**
1. List all timers on the system using: `systemctl list-timers --all`
2. Look for timers associated with the suspicious service found in previous tasks.
3. The timer responsible for scheduling the beacon service is named "bot-beacon.timer".

**Hidden Flag:** bot-beacon.timer

**Hints:**
1. Use this command to list all timers: `systemctl list-timers --all`
2. Look for timers associated with the beacon service.
3. The timer name follows the pattern of the service name with ".timer" appended.

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating the Linux/XorDDoS botnet behavior as described in the MISP event, with tasks designed to match the security profile of an Incident Responder.