# Scenario: Kinsing Cryptominer Investigation

## INFO_LEVEL
The Kinsing malware is a cryptocurrency miner that targets Linux systems. It exploits vulnerabilities to gain access and then spreads laterally to other systems within the network. Your task is to investigate and respond to a Kinsing infection in a controlled environment.

## ACCESS_LEVEL
You have SSH access to the `miner-host` with the username `cyrano` and password `cyrano`. From there, you can investigate the compromised system and any other reachable hosts.

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` for unauthorized or suspicious services running on the system.

**Objective:** Enumerate running services and distinguish legitimate services from malicious miner-related services.

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

**Validation:** The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for abnormal CPU or resource utilization on the `miner-host`.

**Objective:** Analyze running processes and correlate resource consumption with potentially malicious activity.

**Hint:** Use process monitoring tools to identify processes consuming excessive resources.

**Validation:** The hidden flag is the name of the suspicious process.

## TRAINING_LEVEL 3
**Task:** Determine which network port is used for suspicious outbound communication from the `miner-host`.

**Objective:** Investigate network traffic and identify abnormal communication ports.

**Hint:** Check active network connections and look for any unusual outbound ports.

**Validation:** The hidden flag is the port number used for suspicious outbound communication.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Kinsing cryptominer infection, focusing on service discovery, process analysis, and network communication investigation. The scenario ensures that all tasks are feasible within the given sandbox environment and adhere to the constraints provided.