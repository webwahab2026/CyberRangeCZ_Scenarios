# Scenario: Kinsing Cryptominer Investigation

## INFO_LEVEL
The Kinsing malware is a cryptocurrency miner that targets Linux systems. It exploits vulnerabilities to gain access and install malicious components. In this scenario, you will investigate a compromised system to identify and analyze the Kinsing malware's activities.

## ACCESS_LEVEL
You have SSH access to the `miner-host` with the username `cyrano` and password `cyrano`. From there, you can investigate the system and connected hosts.

## TRAINING_LEVEL 1
**Task:** Security monitoring has detected an unusual CPU-intensive process on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. SSH into the `miner-host` using the provided credentials.
2. List all running services using `systemctl list-units --type=service --state=running`.
3. Identify the service with an unusual name or description.
4. The hidden flag is the name of the suspicious service.

**Hints:**
1. Use `systemctl list-units --type=service --state=running` to list all running services.
2. Look for services with unusual names or descriptions.
3. The suspicious service is related to system monitoring.

## TRAINING_LEVEL 2
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Inspect the suspicious service identified in TRAINING_LEVEL 1 using `systemctl cat <service>`.
2. Look for the port number in the service configuration or associated script.
3. The hidden flag is the port number used for communication.

**Hints:**
1. Use `systemctl cat <service>` to inspect the service configuration.
2. Look for the port number in the ExecStart or other relevant fields.
3. The port number is used for communication with an external system.

## TRAINING_LEVEL 3
**Task:** Investigators suspect that a mechanism keeps the miner service running across reboots and process termination. Determine which system component is responsible for this activity.

**Solution:**
1. Check the status of the suspicious service using `systemctl status <service>`.
2. Look for information about the service's persistence mechanism.
3. The hidden flag is the path to the cron job responsible for the service's persistence.

**Hints:**
1. Use `systemctl status <service>` to check the service status.
2. Look for information about the service's persistence mechanism.
3. The cron job path is located in the `/etc/cron.d/` directory.