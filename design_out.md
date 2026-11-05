### Scenario: Adwind/jRAT Incident Response

#### INFO_LEVEL
**Scenario Overview:**
You are an incident responder tasked with investigating a compromised host infected with the Adwind/jRAT trojan. This cross-platform remote access trojan (RAT) is capable of stealing credentials, recording keystrokes, taking screenshots, and exfiltrating data. Your mission is to identify the malicious activities, understand the infection vector, and contain the threat.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service configurations to discover persistence mechanisms.
- Analyze network communication to identify command and control (C2) activities.
- Preserve forensic evidence and contain the threat.

---

#### ACCESS_LEVEL
**Access Information:**
- **Entry Host:** victim (IP: 192.168.60.10)
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**Network Topology:**
- **victim (192.168.60.10):** Compromised host running Adwind/jRAT.
- **dist-server (192.168.60.5):** Distribution server hosting the malicious installer.
- **c2-server (192.168.60.20):** Command and control server receiving exfiltrated data.
- **router (192.168.60.1):** Network router.

---

#### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity of periodically collecting `/etc/passwd`, home directory listings, and sensitive files, then exfiltrating them to a C2 server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   ```bash
   systemctl list-units --type=service --all
   ```
   Look for unfamiliar or suspicious service names.

2. **Inspect Service Details:**
   ```bash
   systemctl cat net-diag-harvest.service
   ```
   Examine the service configuration for suspicious ExecStart paths or descriptions.

3. **Check Service Status:**
   ```bash
   systemctl status net-diag-harvest.service
   ```
   Verify if the service is active and running.

4. **Identify the Service Name:**
   The service responsible for the suspicious activity is `net-diag-harvest.service`.

**Hidden Flag:**
`net-diag-harvest.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. Use `systemctl cat <service>` to inspect the service configuration.

---

#### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the Service Configuration:**
   ```bash
   systemctl cat net-diag-harvest.service
   ```
   Look for the ExecStart path, which contains the script launched by the service.

2. **Examine the Script:**
   ```bash
   cat /usr/local/lib/.netd/harvester.sh
   ```
   Identify the port number used for communication with the C2 server.

3. **Verify the Port:**
   The port number used for exfiltration is `1033`.

**Hidden Flag:**
`1033`

**Hints:**
1. Use `systemctl cat <service>` to inspect the service configuration.
2. Look for the ExecStart path in the service configuration.
3. Examine the script at the specified path to find the port number.

---

#### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the Credential Harvester Service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **List All Timers:**
   ```bash
   systemctl list-timers --all
   ```
   Look for timers associated with the suspicious service.

2. **Inspect the Timer Configuration:**
   ```bash
   systemctl cat net-diag-harvest.timer
   ```
   Examine the timer configuration for details about its activation.

3. **Check Timer Status:**
   ```bash
   systemctl status net-diag-harvest.timer
   ```
   Verify if the timer is active and running.

4. **Identify the Timer Name:**
   The timer responsible for the persistence of the Credential Harvester Service is `net-diag-harvest.timer`.

**Hidden Flag:**
`net-diag-harvest.timer`

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the suspicious service.
3. Use `systemctl cat <timer>` to inspect the timer configuration.

---