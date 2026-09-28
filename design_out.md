# XMRig Cryptominer Investigation

## INFO_LEVEL
The organization has detected unusual CPU usage on several Linux servers. Initial analysis suggests potential cryptocurrency mining activity. Your task is to investigate and contain this threat.

## ACCESS_LEVEL
You have SSH access to the miner-host system with the username `cyrano` and password `cyrano`. From this system, you can investigate the local host and potentially other connected systems.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual CPU usage on the miner-host system.

**Question:** What service is responsible for the abnormal CPU utilization?

**Hint:** Check running services and processes to identify any unusual or unauthorized activity.

## TRAINING_LEVEL 2
**Task:** Determine the network communication associated with the suspicious service.

**Question:** What external IP address is the suspicious service communicating with?

**Hint:** Examine network connections and analyze traffic patterns to identify suspicious communication.

## TRAINING_LEVEL 3
**Task:** Investigate how the malicious service maintains persistence on the system.

**Question:** What system service is used to ensure the malicious software runs automatically after a reboot?

**Hint:** Check system service configurations and look for any unauthorized or suspicious services.

---

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are designed to guide students through investigating a cryptocurrency mining threat while adhering to the constraints and requirements specified.