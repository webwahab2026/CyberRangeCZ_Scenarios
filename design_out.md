# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

### Hint
Focus on unusual services, persistent processes, and network connections that don't match normal operational patterns.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate unusual network connections on the target host.

**Objective:** Identify suspicious network activity that may indicate command and control communication.

**Question:** What port is being used for suspicious outbound connections?

**Hint:** Check active network connections and look for unusual destinations or ports.

## TRAINING_LEVEL 2
**Task:** Analyze the persistence mechanism of the suspicious service.

**Objective:** Determine how the malicious service maintains persistence on the system.

**Question:** What is the name of the systemd service responsible for maintaining persistence?

**Hint:** Examine systemd service files and look for recently created or modified services.

## TRAINING_LEVEL 3
**Task:** Investigate lateral movement indicators.

**Objective:** Identify evidence of lateral movement from the target host to other systems.

**Question:** What script is responsible for transferring files to another host?

**Hint:** Look for scripts in common directories that might be used for file transfers or remote execution.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task focuses on investigating the Sofacy Fysbis backdoor while adhering to the constraints and requirements specified.