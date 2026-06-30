### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
**Scenario Title:** BRICKSTORM Backdoor Investigation

**Objective:**
Investigate and mitigate the presence of the BRICKSTORM backdoor on the target system. This backdoor uses advanced techniques to evade detection, including SOCKS proxying, multi-layered web service communication, and varied command execution.

**Background:**
The BRICKSTORM backdoor has been detected on the target system. Your task is to identify the malicious activity, understand its behavior, and mitigate the threat.

**Learning Objectives:**
- Identify suspicious services and files.
- Investigate lateral movement techniques.
- Mitigate command and control (C2) communication.
- Remove persistence mechanisms.

---

#### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Service

**Description:**
The BRICKSTORM backdoor uses a suspicious service for its operations. Investigate the running services on the target system and identify the malicious service.

**Steps:**
1. Connect to the target system using SSH.
2. List all running services.
3. Identify the suspicious service related to the BRICKSTORM backdoor.

**Flag:** service name

**Hint:**
Check the systemd services and look for any unusual or unfamiliar services.

---

#### TRAINING_LEVEL 2
**Task:** Investigate Lateral Movement

**Description:**
The BRICKSTORM backdoor has been transferring files between hosts for lateral movement. Investigate the file transfer mechanism and identify the service responsible for this activity.

**Steps:**
1. Examine the system logs for any suspicious file transfer activities.
2. Identify the service responsible for the lateral movement.
3. Document the findings.

**Flag:** service name

**Hint:**
Check the system logs for any unusual file transfer activities and look for services that might be responsible for this behavior.

---

#### TRAINING_LEVEL 3
**Task:** Mitigate C2 Communication

**Description:**
The BRICKSTORM backdoor communicates with a command and control (C2) server. Identify the C2 communication and mitigate it to prevent further malicious activity.

**Steps:**
1. Identify the C2 IP address and port used by the backdoor.
2. Block the C2 communication to prevent further malicious activity.
3. Document the steps taken to mitigate the threat.

**Flag:** Port number

**Hint:**
Check the network connections and look for any suspicious outbound connections to external IP addresses.

---