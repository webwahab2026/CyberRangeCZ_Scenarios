Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** TeamTNT Hildegard Malware Investigation

**INFO_LEVEL:**
The TeamTNT hacking group has been detected in your Kubernetes environment. Their Hildegard malware targets Kubernetes clusters, exploiting misconfigured kubelets for initial access. It spreads across containers, establishes C2 connections via tmate reverse shell and IRC channels, disguises processes, uses LD_PRELOAD for process hiding, and encrypts payloads. It performs cryptojacking and searches for cloud credentials.

Your task is to investigate and contain this malware.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Hostname: target
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. SSH into the target host using the provided credentials.
2. List all services using the command: `systemctl list-units --type=service --all`
3. Look for unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. The suspicious service is named `bioset.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Check the status of suspicious services using `systemctl status <service_name>`.

**TRAINING_LEVEL 2:**
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Check the status of the suspicious service identified in the previous task: `systemctl status bioset.service`
2. Look for the port number in the ExecStart command. It should be something like `-lk 4444`.
3. The network port associated with this communication is `4444`.

**Hints:**
1. Use `systemctl status <service_name>` to check the status of the service.
2. Look for the port number in the ExecStart command.
3. The port number is typically the last argument in the ExecStart command.

**TRAINING_LEVEL 3:**
**Task:** System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Solution:**
1. List all timers using the command: `systemctl list-timers --all`
2. Look for timers with unusual names or those that are not part of standard system services.
3. Check the status of suspicious timers using `systemctl status <timer_name>`.
4. The suspicious timer is named `local-inventory.timer`.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with unusual names or those that are not part of standard system services.
3. Check the status of suspicious timers using `systemctl status <timer_name>`.

---

This scenario is designed to be deployed in the KYPO/CyberRangeCZ platform and aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and containment of the TeamTNT Hildegard malware, with a focus on discovering the required information through investigation.