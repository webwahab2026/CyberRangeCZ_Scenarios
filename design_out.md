### INFO_LEVEL
**Scenario Title:** Umbreon Rootkit Investigation

**Scenario Description:**
Security monitoring has detected unusual activity on the victim host, suggesting the presence of a rootkit. Your task is to investigate the compromised system, identify the rootkit's behavior, and determine how it maintains persistence and communicates with the attacker.

**Learning Objectives:**
- Enumerate running services to identify suspicious activities.
- Investigate systemd services and timers for persistence mechanisms.
- Analyze network connections to uncover unauthorized communication.
- Discover hidden privileged user accounts created by the attacker.

### ACCESS_LEVEL
**Entry Host:** victim
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL
**Task 1: Suspicious C2 Beaconing Service Discovery**

**Task Description:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity that periodically sends beacon to the attacker.

**Step-by-Step Solution:**
1. List all running and inactive services using the command:
   ```bash
   systemctl list-units --type=service --all
   ```
2. Look for unfamiliar service names or misspellings of legitimate services. Pay attention to services with unusual descriptions or startup behavior.
3. Identify the service named `espeon.service`, which appears to be related to the suspicious activity.

**Hidden Flag:**
The hidden flag is the name of the suspicious service: `espeon.service`

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services.
2. Look for services with unusual names or descriptions.
3. The suspicious service is related to the beaconing activity.

---

**Task 2: Communication with the Attacker Host Discovery (Port)**

**Task Description:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-Step Solution:**
1. Inspect the beaconing service definition using the command:
   ```bash
   systemctl cat espeon.service
   ```
2. Pay particular attention to the `ExecStart` line, which specifies the path to the script launched by the beacon service.
3. Open the script located at `/home/cyrano/.kit_beacon.sh` and look for the port number used to establish communication with the attacker.
4. The port number used for communication is `4444`.

**Hidden Flag:**
The hidden flag is the port number used for communication: `4444`

**Hints:**
1. Use `systemctl cat espeon.service` to inspect the service definition.
2. Look for the `ExecStart` line in the service definition.
3. Open the script located at `/home/cyrano/.kit_beacon.sh` and search for the port number.

---

**Task 3: Persistence Discovery for Beacon Service**

**Task Description:**
Investigators suspect that a mechanism keeps the beaconing service running across reboots and process termination. Determine which system component is responsible for this activity.

**Step-by-Step Solution:**
1. Check the status of the beaconing service using the command:
   ```bash
   systemctl status espeon.service
   ```
2. Look for any related timers or cron jobs that might be responsible for restarting the service.
3. Use the command to list all timers:
   ```bash
   systemctl list-timers --all
   ```
4. Identify the timer named `udev-helper.timer`, which is responsible for restarting the beaconing service.
5. The path to the cron job is `/etc/cron.d/dbus-cleanup`.

**Hidden Flag:**
The hidden flag is the path to the cron job: `/etc/cron.d/dbus-cleanup`

**Hints:**
1. Use `systemctl status espeon.service` to check the service status.
2. Look for related timers or cron jobs.
3. Use `systemctl list-timers --all` to list all timers.
4. Identify the timer named `udev-helper.timer`.