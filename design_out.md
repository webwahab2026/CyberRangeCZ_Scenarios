### Scenario: PACHA Backdoor Investigation

**INFO_LEVEL:**
The PACHA malware is a Linux server infection that uses coinminers and establishes persistence through various scripts. It communicates with C2 servers and uses iptables rules to manage its activities. Your task is to investigate and respond to this threat.

**ACCESS_LEVEL:**
You have access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can SSH into `next-target` using the same credentials.

---

**TRAINING_LEVEL 1: Suspicious C2 Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Step-by-Step Solution:**
1. SSH into the `target` host using the provided credentials.
2. List all running and inactive services using the command `systemctl list-units --type=service --all`.
3. Look for any unfamiliar or suspicious service names.
4. The suspicious service is named `python.service`.

**Hint 1:**
Use the command `systemctl list-units --type=service --all` to list all services.

**Hint 2:**
Look for services with unusual names or descriptions.

**Hint 3:**
The suspicious service is related to network communication.

---

**TRAINING_LEVEL 2: C2 Communication Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. SSH into the `target` host using the provided credentials.
2. Inspect the suspicious service `python.service` using the command `systemctl cat python.service`.
3. Look for the `ExecStart` line, which specifies the command launched by the service.
4. The port number used by the service is `80`.

**Hint 1:**
Use the command `systemctl cat <service>` to inspect the service configuration.

**Hint 2:**
Look for the `ExecStart` line in the service configuration.

**Hint 3:**
The port number is specified as an argument in the `ExecStart` command.

---

**TRAINING_LEVEL 3: Suspicious Data Collection Service Discovery**

**Task Description:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Step-by-Step Solution:**
1. SSH into the `target` host using the provided credentials.
2. List all timers using the command `systemctl list-timers --all`.
3. Look for any unfamiliar or suspicious timer names.
4. The suspicious timer is named `local-inventory.timer`.

**Hint 1:**
Use the command `systemctl list-timers --all` to list all timers.

**Hint 2:**
Look for timers with unusual names or descriptions.

**Hint 3:**
The suspicious timer is related to data collection.

---

**Flag Validation:**
The hidden flags for each task are as follows:
- TRAINING_LEVEL 1: `python.service`
- TRAINING_LEVEL 2: `80`
- TRAINING_LEVEL 3: `local-inventory.timer`

Each task is designed to guide the student through the investigation process, ensuring they discover the required information through systematic analysis. The hints provide additional guidance without revealing the answers directly.