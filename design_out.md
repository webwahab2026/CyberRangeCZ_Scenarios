# Linux.Bew Backdoor Investigation

## INFO_LEVEL
The organization has detected unusual network activity originating from the target host. Initial analysis suggests a potential compromise involving a Linux backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd services and timers for any unusual configurations.

## TRAINING_LEVEL 3
**Task:** Investigate the network connections made by the suspicious service.

**Question:** What is the destination IP address and port used by the suspicious service for its network connections?

**Hint:** Monitor network connections and look for outbound traffic to unexpected destinations.

## Answer Section
1. **TRAINING_LEVEL 1 Answer:** bkd
2. **TRAINING_LEVEL 2 Answer:** systemd service
3. **TRAINING_LEVEL 3 Answer:** 192.168.40.5:443