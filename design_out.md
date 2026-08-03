# Kinsing Cryptominer Incident Response Scenario

## INFO_LEVEL
The Kinsing malware family is known to target Linux systems with cryptominers and rootkits. It exploits vulnerabilities to achieve remote code execution and maintains persistence through various mechanisms. In this scenario, you will investigate a compromised network where Kinsing has infected multiple hosts.

## ACCESS_LEVEL
You have SSH access to the `miner-host` system with the following credentials:
- Username: cyrano
- Password: cyrano

From this host, you can investigate the local system and potentially reach other compromised hosts in the network.

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on the system.

**Description:**
While monitoring system performance, you noticed unusually high CPU usage on `miner-host`. Investigate the running services to identify any unauthorized or suspicious services that might be responsible for this activity.

**Hint:**
Check the status of all running services and look for any that appear unusual or unauthorized.

**Validation:**
The service name is `sys-monitor`.

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for the abnormal CPU usage.

**Description:**
Now that you've identified the suspicious service, determine which process is consuming the most CPU resources and investigate its characteristics.

**Hint:**
Use process monitoring tools to identify the top CPU-consuming processes and examine their properties.

**Validation:**
The process name is `kinsing`.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Description:**
With the suspicious process identified, locate the executable or file responsible for this malicious activity. This will help you understand how the malware is operating on the system.

**Hint:**
Investigate the file system for any unusual or recently modified files that might be related to the suspicious process.

**Validation:**
The filename is `/usr/local/sbin/kinsing`.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is mapped to real hosts, services, and artifacts within the sandbox, ensuring a realistic and deployable exercise.