Based on the provided MISP Event, Security Profile, Topology, Ansible configuration, and Training Level Examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario: Fysbis Backdoor Investigation**

**INFO_LEVEL:**

The target host in your network has been compromised by the Sofacy group using their Fysbis Linux backdoor. This modular malware establishes command and control (C2) channels, performs lateral movement, and exfiltrates data. Your task is to investigate and contain this threat.

**ACCESS_LEVEL:**
- Target host: `target` (IP: 192.168.50.5)
  - Username: cyrano
  - Password: cyrano
- Next-target host: `next-target` (IP: 192.168.50.6)
  - Username: cyrano
  - Password: cyrano

---

**TRAINING_LEVEL_1:**

**Task:** Suspicious C2 Service Discovery

The target host is exhibiting unusual network behavior. Investigate the running services and identify the service responsible for this suspicious activity.

**Solution:**

1. SSH into the target host using the provided credentials.
   ```bash
   ssh cyrano@192.168.50.5
   ```

2. List all services, including inactive ones, to identify suspicious services.
   ```bash
   systemctl list-units --type=service --all
   ```

3. Look for services with unusual names or descriptions. Pay special attention to services with misspellings or unfamiliar descriptions.

4. Identify the suspicious service: `systemkernelservicedefender.service`

**Hidden Flag:** `systemkernelservicedefender.service`

**Hints:**
1. Use `systemctl` to list all services, including inactive ones.
2. Look for services with unusual names or descriptions.
3. Pay special attention to services with misspellings or unfamiliar descriptions.

**Commands:**
1. `systemctl list-units --type=service --all`
2. `systemctl status <service_name>`
3. `journalctl -u <service_name>`

---

**TRAINING_LEVEL_2:**

**Task:** C2 Communication Discovery (Port)

An unfamiliar network service appears to be involved in unauthorized communication. Investigate the service and determine the network port associated with this communication.

**Solution:**

1. Inspect the suspicious service identified in TRAINING_LEVEL_1 using the `systemctl cat` command.
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```

2. Look for the `ExecStart` line in the service configuration, which specifies the command launched by the service. This line will contain the port number as an argument.
   ```bash
   ExecStart=/bin/sh -c '/usr/bin/ncat -lk 80 -c "cat /var/log/local-inventory/inventory.log" >> /var/log/lab-checkin.log 2>&1'
   ```

3. Identify the port number: `80`

**Hidden Flag:** `80`

**Hints:**
1. Use `systemctl cat` to inspect the service configuration.
2. Look for the `ExecStart` line in the service configuration.
3. The port number is specified as an argument in the `ExecStart` line.

**Commands:**
1. `systemctl cat systemkernelservicedefender.service`
2. `grep ExecStart /etc/systemd/system/systemkernelservicedefender.service`
3. `ss -tulnp | grep 80`

---

**TRAINING_LEVEL_3:**

**Task:** Suspicious File Discovery

Investigation indicates that an unauthorized component is executing files on the compromised host. Identify the file responsible for collecting system information.

**Solution:**

1. Inspect the suspicious service identified in TRAINING_LEVEL_1 using the `systemctl cat` command.
   ```bash
   systemctl cat systemkernelservicedefender.service
   ```

2. Look for the `ExecStart` line in the service configuration, which specifies the command launched by the service. This line will contain the file path being executed.
   ```bash
   ExecStart=/bin/sh -c '/usr/bin/ncat -lk 80 -c "cat /var/log/local-inventory/inventory.log" >> /var/log/lab-checkin.log 2>&1'
   ```

3. Identify the file being executed: `/var/log/local-inventory/inventory.log`

**Hidden Flag:** `/var/log/local-inventory/inventory.log`

**Hints:**
1. Use `systemctl cat` to inspect the service configuration.
2. Look for the `ExecStart` line in the service configuration.
3. The file being executed is specified in the `ExecStart` line.

**Commands:**
1. `systemctl cat systemkernelservicedefender.service`
2. `grep ExecStart /etc/systemd/system/systemkernelservicedefender.service`
3. `ls -lah /var/log/local-inventory/inventory.log`

---

This scenario is strictly aligned with the provided sandbox environment and MISP event, focusing on the investigation and containment of the Fysbis backdoor. Each task is designed to guide students through the process of discovering and remediating the threat while adhering to the constraints and guidelines provided.