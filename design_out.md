### Scenario: Sofacy Fysbis Backdoor Investigation

**INFO_LEVEL:**
The target system has been compromised by the Sofacy group using the Fysbis backdoor. Your task is to investigate the compromised host, identify the malicious activities, and contain the threat.

**ACCESS_LEVEL:**
You have SSH access to the target system with the username `cyrano` and password `cyrano`. The target system's IP address is `192.168.50.5`.

---

### TRAINING_LEVEL 1: Suspicious C2 Service Discovery

**Task:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Hint:**
Look for services with unusual names or descriptions. Pay attention to services that are not part of the standard system configuration.

**Question:**
What is the name of the suspicious service?

---

### TRAINING_LEVEL 2: C2 Communication Discovery (Port)

**Task:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Hint:**
Check the service configuration and network listeners. Look for ports that are not part of the standard system configuration.

**Question:**
What is the network port associated with the suspicious service?

---

### TRAINING_LEVEL 3: Suspicious Data Collection Service Discovery

**Task:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Hint:**
Look for services that collect system information and run periodically. Check the service timers and logs.

**Question:**
What is the name of the service responsible for collecting system information?

---

### Validation

1. **Suspicious C2 Service Discovery:**
   - **Expected Answer:** `systemkernelservicedefender.service`
   - **Validation:** Check if the service name matches the expected answer.

2. **C2 Communication Discovery (Port):**
   - **Expected Answer:** `80`
   - **Validation:** Check if the port number matches the expected answer.

3. **Suspicious Data Collection Service Discovery:**
   - **Expected Answer:** `local-inventory.service`
   - **Validation:** Check if the service name matches the expected answer.

---

### Scenario Conclusion

You have successfully identified the suspicious services and their associated ports. The next steps would involve containing the threat, terminating the malicious processes, and removing the persistent mechanisms to ensure the system is secure.