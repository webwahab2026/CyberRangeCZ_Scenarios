# Scenario: Sofacy Fysbis Backdoor Investigation

## INFO_LEVEL
The target network has been compromised by the Sofacy group using their Fysbis Linux backdoor. Your task is to investigate and respond to this incident.

### Learning Objectives
- Identify and investigate suspicious services
- Determine persistence mechanisms
- Analyze network communications for command-and-control activity
- Collect forensic evidence
- Contain and eradicate the threat

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check running services and look for anything unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers that might be responsible for starting the suspicious service.

## TRAINING_LEVEL 3
**Task:** Analyze the network communications of the suspicious service to identify command-and-control activity.

**Question:** What network port is used for the suspicious communication?

**Hint:** Examine network connections and look for unusual outbound traffic.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. The tasks focus on investigating and responding to the Sofacy Fysbis backdoor compromise, with a defense-oriented approach suitable for intermediate-level cybersecurity professionals.