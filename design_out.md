Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. Here is the scenario:

---

# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL

The Sofacy group, also known as APT29, is a sophisticated cyber espionage group believed to be operating out of Russia. They have been active since at least 2008 and have targeted government, diplomatic, think tank, and private sector organizations.

One of their tools is the Fysbis backdoor, a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of Executable and Linking Format (ELF) binaries. Fysbis can install itself to a victim system with or without root privileges.

In this scenario, you will investigate a compromised Linux host to identify and contain the Fysbis backdoor.

## ACCESS_LEVEL

You have SSH access to the target host with the following credentials:

- Hostname: target
- IP Address: 192.168.50.5
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1

### Task: Suspicious C2 Service Discovery

Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

### Solution:

1. Connect to the target host using SSH:
   ```
   ssh cyrano@192.168.50.5
   ```

2. List all services, including inactive ones:
   ```
   systemctl list-units --type=service --all
   ```

3. Look for unfamiliar service names or misspellings of legitimate services. Pay attention to the service descriptions and startup behavior.

4. Identify the suspicious service. In this case, the service is named `bkd.service`.

### Hints:

1. Use the following command to list all services:
   ```
   systemctl list-units --type=service --all
   ```

2. Look for services with unusual descriptions or startup behavior.

3. The suspicious service is named `bkd.service`.

## TRAINING_LEVEL 2

### Task: C2 Communication Discovery (Port)

An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

### Solution:

1. Check the status of the suspicious service:
   ```
   systemctl status bkd.service
   ```

2. Look for the port number in the service configuration. In this case, the port number is 80.

### Hints:

1. Use the following command to check the status of the service:
   ```
   systemctl status bkd.service
   ```

2. Look for the port number in the service configuration.

3. The port number is 80.

## TRAINING_LEVEL 3

### Task: Suspicious Data Collection Service Discovery

System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

### Solution:

1. List all timers to find periodically executed services:
   ```
   systemctl list-timers --all
   ```

2. Look for timers with unusual descriptions or intervals. In this case, the timer is named `local-inventory.timer`.

### Hints:

1. Use the following command to list all timers:
   ```
   systemctl list-timers --all
   ```

2. Look for timers with unusual descriptions or intervals.

3. The timer is named `local-inventory.timer`.

---

This scenario is designed to be deployed on the KYPO/CyberRangeCZ platform and is strictly aligned with the provided sandbox and MISP event. The tasks are designed to be feasible and aligned with the security profile and training level examples.