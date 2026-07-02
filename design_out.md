### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The BRICKSTORM backdoor is a sophisticated 64-bit ELF executable written in Go, targeting Linux systems. It employs advanced evasion techniques such as SOCKS proxying, multi-layered web service communication, and varied command execution. The backdoor uses Domain over HTTPS (DoH), nested TLS encryption, and abuses legitimate cloud services to evade detection. It is capable of C2 communication, lateral movement, data exfiltration, and persistence.

#### ACCESS_LEVEL
- **Entry Host:** `target` (IP: 192.168.50.5)
- **Username:** `cyrano`
- **Password:** `cyrano`
- **Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious service running on the target host.
**Description:** Investigate the services running on the target host and identify the suspicious service related to the BRICKSTORM backdoor.
**Hint:** Check the systemd services and look for any unusual or unfamiliar services.
**Flag:** `updatemgr.service`

#### TRAINING_LEVEL 2
**Task:** Investigate the suspicious outbound IP and port.
**Description:** Analyze the network connections on the target host to identify any suspicious outbound IP addresses and ports used by the BRICKSTORM backdoor for C2 communication.
**Hint:** Use tools like `netstat`, `ss`, or `tcpdump` to inspect network connections.
**Flag:** `192.168.40.5:443`

#### TRAINING_LEVEL 3
**Task:** Identify the file transfer mechanism for lateral movement.
**Task:** Investigate the file transfer mechanism used by the BRICKSTORM backdoor for lateral movement between the target and next-target hosts.
**Description:** Examine the system logs and processes to identify the service responsible for transferring files between the hosts.
**Hint:** Check the systemd services and logs for any file transfer activities.
**Flag:** `payload-transfer.service`