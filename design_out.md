### INFO_LEVEL

**Scenario Title:** Rhombus Botnet Investigation

**Scenario Description:**
Security monitoring has detected unusual network activity originating from several Linux hosts in your organization's infrastructure. Initial analysis suggests these hosts may be compromised by the Rhombus botnet, a Linux DDoS botnet targeting VPS and IoT devices. Your task is to investigate the compromised hosts, identify the malicious activities, and implement appropriate containment measures.

**Learning Objectives:**
- Enumerate and analyze running services and systemd timers to identify suspicious activities.
- Investigate network connections and service configurations to determine communication endpoints.
- Identify and disable persistence mechanisms to prevent unauthorized activities from restarting.
- Contain the threat by blocking unauthorized network communication.
- Terminate malicious processes and remove malicious artifacts to remediate the compromise.

**Prerequisites:**
- Basic knowledge of Linux command line and system administration.
- Familiarity with systemd service management.
- Understanding of network security principles and common attack vectors.

---

### ACCESS_LEVEL

**Entry Host:**
- Hostname: `bot1`
- Username: `cyrano`
- Password: `cyrano`

**Access Method:**
- SSH access is available to the entry host `bot1`. Use the provided credentials to log in and begin your investigation.

**Network Topology:**
- The compromised hosts (`bot1`, `bot2`) are connected to the `botnet-switch` network (192.168.70.0/24).
- The victim host (`victim`) is connected to the `victim-switch` network (192.168.80.0/24).
- The C2 server (`c2-server`) is connected to the `botnet-switch` network (192.168.70.5).

---

### TRAINING_LEVEL 1

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-Step Solution:**
1. Log in to the entry host `bot1` using the provided credentials.
2. Enumerate all running and inactive services using the following command:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar service names or misspellings of legitimate services. Pay attention to services with unusual descriptions or startup behavior.
4. Identify the service responsible for sending beacon periodically to the C2 Server. The hidden flag is the name of this service.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Check the status of suspicious services using `systemctl status <service>`.

---

### TRAINING_LEVEL 2

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. From the entry host `bot1`, inspect the service identified in the previous task using the following command:
   ```
   systemctl cat <service>
   ```
2. Pay particular attention to the `ExecStart` line, which specifies the path of the script launched by the service.
3. Check the script to find the communication port with the C2 server. The hidden flag is the port number.

**Hints:**
1. Use `systemctl cat <service>` to view the service configuration.
2. Look for the `ExecStart` line in the service configuration.
3. Inspect the script specified in `ExecStart` to find the communication port.

---

### TRAINING_LEVEL 3

**Task Description:**
Investigators suspect that the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-Step Solution:**
1. From the entry host `bot1`, list all systemd timers using the following command:
   ```
   systemctl list-timers --all
   ```
2. Identify the timer associated with the C2 beacon service. The hidden flag is the name of this timer.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers with names related to the C2 beacon service.
3. Check the status of suspicious timers using `systemctl status <timer>`.

---

**Note:** The scenario is designed to be deployed in the KYPO/CyberRangeCZ environment, ensuring strict alignment with the provided sandbox topology and MISP event. All tasks and solutions are consistent with the sandbox's reality and the security profile's requirements.