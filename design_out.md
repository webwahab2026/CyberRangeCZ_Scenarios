# XMRig Cryptominer Investigation

## INFO_LEVEL
This scenario presents a compromised Linux host running a cryptocurrency miner. Your task is to investigate the infection, identify the malicious components, and contain the threat.

The compromised host is `miner-host` with IP address `192.168.50.5`. You have SSH access to this host with the username `cyrano` and password `cyrano`.

## ACCESS_LEVEL
- Entry host: `miner-host` (192.168.50.5)
- Username: cyrano
- Password: cyrano
- Access method: SSH

## TRAINING_LEVEL 1
**Task:** Security monitoring has detected an unusual CPU-intensive process on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Solution:**
1. Connect to the miner-host using SSH: `ssh cyrano@192.168.50.5`
2. List all services: `systemctl list-units --type=service --all`
3. Identify the suspicious service by looking for unusual service names or high CPU usage
4. Check the status of the suspicious service: `systemctl status bash.service`
5. The hidden flag is the name of the suspicious service.

**Hints:**
1. Use `ps aux --sort=-%cpu` to identify the process consuming the most CPU resources.
2. Check the service status with `systemctl status <service>`.
3. Look for services with unusual names or descriptions.

## TRAINING_LEVEL 2
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Solution:**
1. Check the service configuration: `systemctl cat bash.service`
2. Look for the port number in the ExecStart parameter
3. The hidden flag is the port number.

**Hints:**
1. Use `ss -tulnp` to list all listening ports.
2. Check the service configuration with `systemctl cat <service>`.
3. Look for the port number in the ExecStart parameter.

## TRAINING_LEVEL 3
**Task:** Investigators suspect that a mechanism keeps the miner service running across reboots and process termination. Determine which system component is responsible for this activity.

**Solution:**
1. Check the service status: `systemctl status bash.service`
2. Look for the path to the cron job file in the output
3. The hidden flag is the path to the cron job file.

**Hints:**
1. Use `grep -Rni . /etc/cron.d/ 2>/dev/null` to search for cron jobs.
2. Check the service status with `systemctl status <service>`.
3. Look for the path to the cron job file in the output.