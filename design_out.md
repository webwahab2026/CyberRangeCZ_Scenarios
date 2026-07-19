### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The BRICKSTORM backdoor is a sophisticated 64-bit ELF executable written in Go, designed to evade detection through advanced techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution. This backdoor has been observed using Domain Name System (DNS) over HTTPS (DoH), nested TLS encryption, and abusing legitimate cloud services to hide its activities. The malware exhibits command-and-control (C2) capabilities, lateral movement, data exfiltration, and persistence mechanisms.

Your task is to investigate the compromised environment, identify the persistence mechanisms, trace the C2 communication, and detect lateral movement to a secondary target.

#### ACCESS_LEVEL
- **Entry Host:** `target`
- **Username:** `cyrano`
- **Password:** `cyrano`
- **Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious service running on the target host that is responsible for C2 communication.

**Description:**
Investigate the running services on the `target` host. Identify the service that is listening on port 443 and is responsible for C2 communication.

**Hint:**
Check the systemd services and look for any suspicious services that might be related to C2 communication.

**Flag:**
The flag is the name of the service responsible for C2 communication.

#### TRAINING_LEVEL 2
**Task:** Identify the persistence mechanism used by the BRICKSTORM backdoor.

**Description:**
Examine the systemd services and timers on the `target` host. Identify the persistence mechanism that ensures the backdoor service runs continuously.

**Hint:**
Look for systemd services and timers that might be related to the backdoor's persistence.

**Flag:**
The flag is the name of the service or timer responsible for the persistence mechanism.

#### TRAINING_LEVEL 3
**Task:** Detect the lateral movement mechanism used by the BRICKSTORM backdoor.

**Description:**
Investigate the network connections and services on the `target` host. Identify the mechanism used for lateral movement to the `next-target` host.

**Hint:**
Check the systemd services and look for any services that might be transferring data to the `next-target` host.

**Flag:**
The flag is the name of the service responsible for the lateral movement mechanism.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide participants through the investigation of the BRICKSTORM backdoor, focusing on identifying C2 communication, persistence mechanisms, and lateral movement.