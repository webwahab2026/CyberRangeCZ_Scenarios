Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario: Investigating and Containing the Linux/Rakos Backdoor**

**INFO_LEVEL:**
The organization has detected unusual network activity on one of its Linux servers. Initial analysis suggests a possible backdoor infection. Your task is to investigate the compromised host, identify the malicious activity, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target host with the following credentials:
- Hostname: target
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-step solution:**
1. Connect to the target host using SSH with the provided credentials.
2. List all services on the system using the command: `systemctl list-units --type=service --all`
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that are not part of standard system services.
4. Identify the suspicious service name.

**Hint 1:** Use the command `systemctl list-units --type=service --state=running` to list only the running services.
**Hint 2:** Look for services with unusual names or descriptions that do not match standard system services.
**Hint 3:** The suspicious service might have a name that is similar to a legitimate service but with a slight variation.

**TRAINING_LEVEL 2:**
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-step solution:**
1. From the previous task, you have identified the suspicious service name.
2. Inspect the service configuration using the command: `systemctl cat <service_name>`
3. Look for the `ExecStart` line in the service configuration, which specifies the command launched by the service.
4. Identify the port number mentioned in the `ExecStart` command.
5. Alternatively, you can use the command `ss -tulnp` to list all listening ports and their associated processes.

**Hint 1:** The port number is usually specified as an argument to the command in the `ExecStart` line.
**Hint 2:** If you are unsure about the service name, you can list all services and their associated ports using the command `ss -tulnp`.
**Hint 3:** The port number is likely to be a four-digit number.

**TRAINING_LEVEL 3:**
**Task:** System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-step solution:**
1. List all timers on the system using the command: `systemctl list-timers --all`
2. Look for any unfamiliar or suspicious timer names. Pay attention to timers with unusual descriptions or those that are not part of standard system timers.
3. Identify the suspicious timer name.
4. Inspect the timer configuration using the command: `systemctl cat <timer_name>`
5. Look for the `Unit` line in the timer configuration, which specifies the service that the timer activates.
6. The service mentioned in the `Unit` line is responsible for the automatic collection of system information.

**Hint 1:** Use the command `systemctl list-unit-files --type=timer` to list all timer unit files.
**Hint 2:** Look for timers with unusual names or descriptions that do not match standard system timers.
**Hint 3:** The timer might have a name that is similar to a legitimate timer but with a slight variation.

---

This scenario is designed to be deployed in the KYPO/CyberRangeCZ platform and aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and containment of the Linux/Rakos backdoor malware, with a focus on discovering the required information through investigation rather than revealing hidden implementation details.