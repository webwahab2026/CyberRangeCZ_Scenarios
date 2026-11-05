Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a Rhombus botnet infection on Linux systems.

### Scenario: Rhombus Botnet Investigation and Response

#### INFO_LEVEL
The security team has detected unusual network activity originating from several Linux systems in your environment. Initial analysis suggests these systems may be infected with the Rhombus botnet, which is known to target VPS and IoT devices. Your task is to investigate these systems, identify the malicious components, and implement appropriate containment measures.

#### ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- `bot1` (192.168.70.10)
- `bot2` (192.168.70.11)
- `c2-server` (192.168.70.5)

You can use standard Linux commands and tools to investigate these systems.

#### TRAINING_LEVEL 1
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Solution:**
1. SSH into `bot1` using the provided credentials.
2. List all systemd services to identify suspicious ones:
   ```
   systemctl list-units --type=service --all
   ```
3. Look for unfamiliar or suspicious service names, such as those with unusual descriptions or misspellings of legitimate services.
4. The suspicious service is likely named `bot-beacon.service`.

**Hidden Flag:** `bot-beacon.service`

**Hints:**
1. Use `systemctl` commands to list all services and look for anything unusual.
2. Pay attention to service descriptions and names that don't match standard system services.
3. The suspicious service is likely related to network communication.

#### TRAINING_LEVEL 2
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. On `bot1`, inspect the suspicious service identified in the previous task:
   ```
   systemctl cat bot-beacon.service
   ```
2. Look for the `ExecStart` line, which specifies the path of the script launched by the service.
3. Inspect the script at `/usr/local/lib/.botcache/beacon.sh` to find the communication port with the C2 server:
   ```
   cat /usr/local/lib/.botcache/beacon.sh
   ```
4. The script will show the port number used for communication.

**Hidden Flag:** `2222`

**Hints:**
1. Use `systemctl cat` to inspect the service configuration.
2. Look for the `ExecStart` line to find the script path.
3. Inspect the script to find the communication port.

#### TRAINING_LEVEL 3
**Task:** Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Solution:**
1. On `bot1`, list all systemd timers to identify the one responsible for scheduling the suspicious service:
   ```
   systemctl list-timers --all
   ```
2. Look for a timer associated with the `bot-beacon.service`.
3. The timer is likely named `bot-beacon.timer`.

**Hidden Flag:** `bot-beacon.timer`

**Hints:**
1. Use `systemctl list-timers` to identify the timer responsible for scheduling the service.
2. Look for a timer associated with the `bot-beacon.service`.
3. The timer name will be similar to the service name but with a `.timer` suffix.

This scenario provides a structured approach to investigating and responding to a Rhombus botnet infection, aligning with the provided MISP event, security profile, and sandbox environment. The tasks are designed to guide students through the investigation process while adhering to the constraints and requirements outlined.