### INFO_LEVEL
**Scenario Title:** ELF_IMEIJ Backdoor Investigation

**Scenario Description:**
A suspicious service has been detected on the target host. Your task is to investigate and respond to this potential ELF_IMEIJ backdoor threat. The malware is known to exploit CGI vulnerabilities to download and execute malicious payloads. Your goal is to identify, contain, and eradicate the threat.

**Learning Objectives:**
- Identify and investigate suspicious services.
- Determine persistence mechanisms.
- Analyze network communication for command-and-control (C2) activity.
- Contain and eradicate the threat.

---

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery

**Description:**
While monitoring the target host, you noticed an unusual service running. Investigate the running services on the target host and identify any suspicious or unauthorized services.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the systemd services and look for any services that seem out of place or have unusual configurations.

**Validation:**
The hidden flag is the name of the suspicious service.

---

### TRAINING_LEVEL 2
**Task:** Persistence Discovery

**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after a system reboot. Investigate the persistence mechanisms used by the service.

**Learning Objective:**
Identify persistence mechanisms such as systemd, cron, or scheduled tasks.

**Hint:**
Examine the systemd service files and timers to see how the service is configured to start automatically.

**Validation:**
The hidden flag is the name of the persistence mechanism or identifier.

---

### TRAINING_LEVEL 3
**Task:** C2 Communication Discovery (Port)

**Description:**
The suspicious service appears to be communicating with an external command-and-control (C2) server. Determine which network port is used for this communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Use network monitoring tools to observe the outgoing connections from the target host.

**Validation:**
The hidden flag is the C2 port number.

---