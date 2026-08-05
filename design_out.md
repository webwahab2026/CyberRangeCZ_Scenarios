# Scenario: Kinsing Cryptominer Investigation

## INFO_LEVEL
The Kinsing malware family is known to target Linux systems with cryptominers and rootkits. It exploits vulnerabilities to infect systems and establishes persistence mechanisms. In this scenario, you will investigate a compromised network where Kinsing has been detected.

## ACCESS_LEVEL
You have SSH access to the `miner-host` with the username `cyrano` and password `cyrano`. From this host, you can investigate the local system and potentially other connected hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the suspicious service running on the host.

**Description:**
While monitoring system performance, you noticed unusually high CPU usage on `miner-host`. Investigate the running services to identify any unauthorized or suspicious services that might be responsible for this activity.

**Hint:**
Check the status of all running services and look for any that appear unusual or unauthorized.

**Validation:**
The service name is `sys-monitor`.

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for the abnormal CPU usage.

**Description:**
Now that you have identified the suspicious service, determine which process is responsible for the high CPU usage. This will help you understand the nature of the malicious activity.

**Hint:**
Use process monitoring tools to identify the process consuming the most CPU resources.

**Validation:**
The process name is `kinsing`.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity.

**Description:**
With the suspicious process identified, locate the executable or file associated with this process. This will help you understand how the malware is being executed and where it is stored on the system.

**Hint:**
Check the paths and binaries associated with the suspicious process.

**Validation:**
The filename is `/usr/local/sbin/kinsing`.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Kinsing cryptominer infection, focusing on identifying suspicious services, processes, and associated files. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.