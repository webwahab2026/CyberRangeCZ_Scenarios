# Linux/NyaDrop Incident Response Scenario

## INFO_LEVEL
**Scenario Title:** Linux/NyaDrop Backdoor Investigation

**Objective:**
Investigate and respond to a Linux/NyaDrop backdoor infection on an IoT device network. Your goal is to identify the malicious activity, contain the threat, and remove all traces of the malware.

**Background:**
You are part of the incident response team for a company that manages a network of IoT devices. Recent monitoring has detected unusual network activity on one of the devices. Your task is to investigate this activity, identify the source of the problem, and take appropriate action to mitigate the threat.

**Skills Tested:**
- Malware analysis
- Incident response
- Threat containment
- Digital forensics

## ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

## TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery

**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the running services on the target host to identify any unauthorized or suspicious services.

**Question:**
What is the name of the suspicious service running on the target host?

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

## TRAINING_LEVEL 2
**Task:** Persistence Discovery

**Description:**
Now that you have identified the suspicious service, determine how it is being automatically started after reboot. Understanding the persistence mechanism is crucial for complete removal of the malware.

**Question:**
What is the persistence mechanism used by the suspicious service?

**Hint:**
Examine the systemd service files and timers to understand how the service is scheduled to run.

## TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)

**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Identify the network port used for this communication to help contain the threat.

**Question:**
Which network port is used for the suspicious communication?

**Hint:**
Investigate the network connections and listen ports associated with the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is mapped to real hosts, services, and artifacts within the sandbox, ensuring a realistic and deployable exercise.