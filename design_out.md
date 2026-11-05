Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I have designed a deployable scenario for the KYPO/CyberRangeCZ platform. Here is the scenario:

---

# Scenario: BlackTech PLEAD Backdoor Investigation

## INFO_LEVEL

The BlackTech threat group has been linked to cyber espionage campaigns targeting various organizations. Their malware, known as PLEAD, is a backdoor that establishes command and control (C2) communication, performs lateral movement, and exfiltrates data. Your task is to investigate a compromised host within your network that shows signs of PLEAD infection.

## ACCESS_LEVEL

You have SSH access to the compromised host `target` with the following credentials:
- Username: cyrano
- Password: cyrano

You can use this access to investigate the host and gather evidence of the PLEAD backdoor.

## TRAINING_LEVEL 1

### Task: Suspicious C2 Service Discovery

Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

### Step-by-Step Solution:

1. **List all services**: Use the `systemctl` command to list all services on the host.
   ```
   systemctl list-units --type=service --all
   ```

2. **Filter running services**: Narrow down the list to only running services.
   ```
   systemctl list-units --type=service --state=running
   ```

3. **Inspect service details**: Look for any unfamiliar or suspicious services. Pay attention to their descriptions and paths.
   ```
   systemctl cat <service>
   ```

4. **Identify the suspicious service**: Based on the descriptions and paths, identify the service responsible for the suspicious activity.

### Hints:

1. **List all services**: Use the `systemctl list-units --type=service --all` command to see all services.
   ```
   systemctl list-units --type=service --all
   ```

2. **Filter running services**: Use the `systemctl list-units --type=service --state=running` command to see only running services.
   ```
   systemctl list-units --type=service --state=running
   ```

3. **Inspect service details**: Use the `systemctl cat <service>` command to inspect the details of a specific service.
   ```
   systemctl cat <service>
   ```

The hidden flag for this task is the name of the suspicious service.

## TRAINING_LEVEL 2

### Task: C2 Communication Discovery (Port)

An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

### Step-by-Step Solution:

1. **Inspect the suspicious service**: Use the `systemctl cat` command to inspect the details of the suspicious service identified in the previous task.
   ```
   systemctl cat <service>
   ```

2. **Identify the port**: Look for the port number in the service configuration, typically specified in the `ExecStart` line.
   ```
   systemctl cat <service>
   ```

3. **Verify the port**: Use the `ss` command to verify that the port is being listened on.
   ```
   ss -tulnp
   ```

### Hints:

1. **Inspect the suspicious service**: Use the `systemctl cat <service>` command to inspect the details of the suspicious service.
   ```
   systemctl cat <service>
   ```

2. **Identify the port**: Look for the port number in the service configuration, typically specified in the `ExecStart` line.
   ```
   systemctl cat <service>
   ```

3. **Verify the port**: Use the `ss -tulnp` command to verify that the port is being listened on.
   ```
   ss -tulnp
   ```

The hidden flag for this task is the C2 port number.

## TRAINING_LEVEL 3

### Task: Suspicious Data Collection Service Discovery

System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

### Step-by-Step Solution:

1. **List all services**: Use the `systemctl` command to list all services on the host.
   ```
   systemctl list-units --type=service --all
   ```

2. **List all timers**: Use the `systemctl` command to list all timers on the host.
   ```
   systemctl list-timers --all
   ```

3. **Inspect timer details**: Look for any unfamiliar or suspicious timers. Pay attention to their descriptions and paths.
   ```
   systemctl cat <timer>
   ```

4. **Identify the suspicious service**: Based on the descriptions and paths, identify the service responsible for the suspicious activity.
   ```
   systemctl cat <service>
   ```

### Hints:

1. **List all services**: Use the `systemctl list-units --type=service --all` command to see all services.
   ```
   systemctl list-units --type=service --all
   ```

2. **List all timers**: Use the `systemctl list-timers --all` command to see all timers.
   ```
   systemctl list-timers --all
   ```

3. **Inspect timer details**: Use the `systemctl cat <timer>` command to inspect the details of a specific timer.
   ```
   systemctl cat <timer>
   ```

The hidden flag for this task is the name of the suspicious service.

---

This scenario is designed to be deployable on the KYPO/CyberRangeCZ platform and aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of the PLEAD backdoor malware, with a focus on discovering the suspicious service, identifying the C2 communication port, and uncovering the data collection service.