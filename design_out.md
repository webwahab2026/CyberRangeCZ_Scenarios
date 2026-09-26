# Kinsing Cryptominer Incident Response Scenario

## INFO_LEVEL
The Kinsing malware is a cryptocurrency miner that exploits Linux systems. It spreads through vulnerabilities and installs cryptocurrency miners and rootkits, leading to remote code execution (RCE). The malware targets Apache ActiveMQ and uses various persistence mechanisms.

## ACCESS_LEVEL
You are an incident responder with access to the compromised network. Your entry point is the `miner-host` with the following credentials:
- Hostname: `miner-host`
- Username: `cyrano`
- Password: `cyrano`

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` and identify any unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and distinguish legitimate services from malicious miner-related services.
**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.
**Validation:** The service name must be identified and reported.

## TRAINING_LEVEL 2
**Task:** Analyze the `miner-host` for abnormal CPU or resource utilization and identify the process responsible.
**Objective:** Analyze running processes and correlate resource consumption with potentially malicious activity.
**Hint:** Use process monitoring tools to identify processes consuming excessive resources.
**Validation:** The process name must be identified and reported.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity on the `miner-host`.
**Objective:** Correlate suspicious processes or services with files on disk and identify malicious artifacts.
**Hint:** Investigate the paths and properties of running processes to find associated files.
**Validation:** The filename or file path must be identified and reported.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident responders.