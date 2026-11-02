### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The Sofacy group, also known as APT29, is a sophisticated cyber espionage group believed to be operating out of Russia. They are known for targeting government, diplomatic, and military organizations. One of their tools is the Fysbis backdoor, a modular Linux trojan/backdoor that implements plug-in and controller modules as distinct classes. It includes both 32-bit and 64-bit versions of Executable and Linking Format (ELF) binaries. Fysbis can install itself to a victim system with or without root privileges. It has capabilities for remote shell control, local reconnaissance, and establishing persistence.

**ACCESS_LEVEL:**
You have been given access to a compromised Linux host named `target` with the username `cyrano` and password `cyrano`. Your goal is to investigate the host, identify the malicious activity, and contain the threat.

**TRAINING_LEVEL 1:**
**Task:** Suspicious C2 Service Discovery
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. SSH into the `target` host using the provided credentials.
2. List all running services using the command `systemctl list-units --type=service --state=running`.
3. Look for any unfamiliar or suspicious service names. Pay attention to services with unusual descriptions or those that you do not recognize as legitimate system services.
4. The suspicious service is named `systemkernelservicedefender.service`.

**Hint 1:** Use the command `systemctl list-units --type=service --state=running` to list all running services.
**Hint 2:** Look for services with unusual or unfamiliar names.
**Hint 3:** The suspicious service has a name that includes "kernel" and "defender".

**TRAINING_LEVEL 2:**
**Task:** C2 Communication Discovery (Port)
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Inspect the suspicious service using the command `systemctl cat systemkernelservicedefender.service`.
2. Look for the `ExecStart` line in the service definition. This line specifies the command launched by the service and includes the port number as an argument.
3. The port number used by the suspicious service is `80`.

**Hint 1:** Use the command `systemctl cat systemkernelservicedefender.service` to inspect the service definition.
**Hint 2:** Look for the `ExecStart` line in the service definition.
**Hint 3:** The port number is specified as an argument in the `ExecStart` command.

**TRAINING_LEVEL 3:**
**Task:** Suspicious Data Collection Service Discovery
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Solution:**
1. List all systemd timers using the command `systemctl list-timers --all`.
2. Look for any unfamiliar or suspicious timers. Pay attention to timers with unusual descriptions or those that you do not recognize as legitimate system timers.
3. The suspicious timer is named `local-inventory.timer`.

**Hint 1:** Use the command `systemctl list-timers --all` to list all systemd timers.
**Hint 2:** Look for timers with unusual or unfamiliar names.
**Hint 3:** The suspicious timer has a name that includes "inventory".