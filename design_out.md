# BRICKSTORM Backdoor Investigation

## INFO_LEVEL
The target host has exhibited unusual network activity, including connections to unknown external servers. Initial analysis suggests the presence of a sophisticated backdoor named BRICKSTORM. Your task is to investigate and contain this threat.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network connections on the target host.

**Question:** What port is being used for the suspicious outbound connections?

**Hint:** Check the network connections and look for unusual destinations or ports.

## TRAINING_LEVEL 2
**Task:** Identify the process responsible for the suspicious network activity.

**Question:** What is the name of the process making the suspicious connections?

**Hint:** Use process enumeration tools to find the process and its associated files.

## TRAINING_LEVEL 3
**Task:** Determine how the malicious process maintains persistence on the system.

**Question:** What is the name of the service or mechanism ensuring the malicious process runs after reboot?

**Hint:** Investigate system startup configurations and look for unusual entries.

---

**Validation:**

1. **TRAINING_LEVEL 1:**
   - Expected Answer: `443`
   - Validation: The answer must match the port used for the suspicious outbound connections.

2. **TRAINING_LEVEL 2:**
   - Expected Answer: `updatemgr`
   - Validation: The answer must match the name of the process making the suspicious connections.

3. **TRAINING_LEVEL 3:**
   - Expected Answer: `updatemgr.service`
   - Validation: The answer must match the name of the service or mechanism ensuring the malicious process runs after reboot.

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging exercise for incident response training.