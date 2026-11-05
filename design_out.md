### Scenario: Linux.Proxy.10 Incident Response

#### INFO_LEVEL
**Scenario Overview:**
You are an incident responder tasked with investigating a compromised Linux host infected with the Linux.Proxy.10 trojan. This trojan is designed to run a SOCKS5 proxy server on infected Linux devices, allowing cybercriminals to remain anonymous online. Your goal is to identify the malicious activities, understand the infection vector, and contain the threat.

**Learning Objectives:**
- Enumerate running and inactive services to identify suspicious activities.
- Investigate systemd service configurations to understand persistence mechanisms.
- Analyze network communication to identify unauthorized data exfiltration.

---

#### ACCESS_LEVEL
**Access Information:**
- **Entry Host:** victim (IP: 192.168.60.10)
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH

**Network Topology:**
- **victim (192.168.60.10):** Compromised host running the trojan.
- **dist-server (192.168.60.5):** Server used to distribute the trojan.
- **c2-server (192.168.60.20):** Command and control server.
- **router (192.168.60.1):** Network router.

---

#### TRAINING_LEVEL 1
**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity of periodically collecting `/etc/passwd`, home directory listings, and sensitive files, then exfiltrating them to a C2 server.

**Step-by-Step Solution:**
1. **Enumerate Running Services:**
   - Use `systemctl list-units --type=service --all` to list all services.
   - Look for unfamiliar or suspicious service names.

2. **Inspect Service Configurations:**
   - Use `systemctl cat <service>` to inspect the configuration of suspicious services.
   - Pay attention to the `ExecStart` field, which specifies the script launched by the service.

3. **Identify the Suspicious Service:**
   - The service responsible for the suspicious activity is likely named `net-diag-harvest.service`.
   - Verify the service description and the script it launches.

**Hidden Flag:**
The name of the suspicious service is `net-diag-harvest.service`.

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual descriptions or startup behavior.
3. Use `systemctl cat <service>` to inspect the configuration of suspicious services.

---

#### TRAINING_LEVEL 2
**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system for exfiltrating data to a C2 server. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. **Inspect the Suspicious Service:**
   - Use `systemctl cat net-diag-harvest.service` to inspect the service configuration.
   - Pay particular attention to the `ExecStart` field, which specifies the path to the script launched by the service.

2. **Analyze the Script:**
   - Use `cat /usr/local/lib/.netd/harvester.sh` to inspect the script.
   - Look for the port number used to establish communication with the C2 server.

**Hidden Flag:**
The network port associated with the communication is `18902`.

**Hints:**
1. Use `systemctl cat net-diag-harvest.service` to inspect the service configuration.
2. Look for the `ExecStart` field in the service configuration.
3. Use `cat /usr/local/lib/.netd/harvester.sh` to inspect the script and find the port number.

---

#### TRAINING_LEVEL 3
**Task Description:**
Investigators suspect that a mechanism keeps the Credential Harvester Service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. **List All Timers:**
   - Use `systemctl list-timers --all` to list all timers.
   - Look for timers associated with the suspicious service.

2. **Inspect the Timer Configuration:**
   - Use `systemctl cat net-diag-harvest.timer` to inspect the timer configuration.
   - Verify the timer's description and the service it activates.

**Hidden Flag:**
The timer responsible for the persistence of the Credential Harvester Service is `net-diag-harvest.timer`.

**Hints:**
1. Use `systemctl list-timers --all` to list all timers.
2. Look for timers associated with the suspicious service.
3. Use `systemctl cat net-diag-harvest.timer` to inspect the timer configuration.

---