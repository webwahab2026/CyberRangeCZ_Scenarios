# Linux/NyaDrop Incident Response Scenario

## INFO_LEVEL
**Scenario Title:** Linux/NyaDrop Backdoor Investigation

**Objective:**
Investigate and respond to a Linux/NyaDrop backdoor malware infection on an IoT device network. Your goal is to identify the malicious activity, contain the threat, and remove the malware from the compromised systems.

**Background:**
You are an incident responder for a company that manages a network of MIPS-based IoT devices. Recent network monitoring has detected suspicious outbound connections from one of the devices. Your task is to investigate this activity, identify the source of the infection, and take appropriate action to contain and remove the threat.

## ACCESS_LEVEL
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

## TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the network, you noticed unusual outbound connections from the target host. Investigate the target host to identify any unauthorized or suspicious services running on the system.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the list of running services and look for any that seem out of place or unfamiliar.

## TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
You have identified a suspicious service running on the target host. Determine how this service is automatically started after reboot.

**Learning Objective:**
Identify persistence mechanisms (e.g., systemd, cron, scheduled task).

**Hint:**
Investigate the systemd services and timers to find any related to the suspicious service.

## TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)
**Description:**
The suspicious service appears to be communicating with an external command-and-control server. Determine which network port is used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Examine the network connections and listen ports to find the one used by the suspicious service.

---

**Validation:**
1. Suspicious Service Discovery: The student should identify the `nyadrop.service` as the suspicious service.
2. Persistence Discovery: The student should find that the service is started by the `nyadrop.service` systemd unit.
3. C2 Communication Discovery (Port): The student should determine that the service is using port 4444 for communication.

This scenario provides a structured approach to investigating and responding to a Linux/NyaDrop backdoor malware infection, aligning with the Incident Response security profile and the provided sandbox environment.