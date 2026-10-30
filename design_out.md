### Scenario: Sofacy Fysbis Backdoor Investigation

**Difficulty Level:** Intermediate
**Cybersecurity Approach:** Defence-oriented
**Scenario Type:** Exercise
**Include Q/A:** true
**Include Hint:** true

---

#### INFO_LEVEL
**Scenario Background:**
Security monitoring has detected unusual network activity involving a Linux host in your environment. Initial analysis suggests the presence of a backdoor associated with the Sofacy group, specifically the Fysbis malware. Your task is to investigate the compromised host, identify the malicious components, and take appropriate containment measures.

**Learning Objectives:**
- Enumerate and analyze system services to identify unauthorized components.
- Investigate network connections and service configurations to detect suspicious communication.
- Discover and disable persistence mechanisms.
- Collect and preserve forensic evidence.
- Apply appropriate containment measures to prevent further unauthorized activity.

---

#### ACCESS_LEVEL
**Access Information:**
- **Entry Host:** `target` (IP: 192.168.50.5)
- **Username:** `cyrano`
- **Password:** `cyrano`
- **Access Method:** SSH

**Network Topology:**
- **C2 Server:** `c2-server` (IP: 192.168.40.5)
- **Target Host:** `target` (IP: 192.168.50.5)
- **Next Target Host:** `next-target` (IP: 192.168.50.6)

---

#### TRAINING_LEVEL 1
**Task:**
Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.

**Question:**
What is the name of the suspicious service responsible for the unauthorized activity?

**Hint:**
Use systemd commands to list all services and look for any that appear unusual or unauthorized.

**Answer:**
systemkernelservicedefender.service

---

#### TRAINING_LEVEL 2
**Task:**
An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Question:**
What is the network port associated with the suspicious service?

**Hint:**
Use network enumeration commands to identify listening ports and correlate them with the suspicious service.

**Answer:**
80

---

#### TRAINING_LEVEL 3
**Task:**
System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.

**Question:**
What is the name of the service responsible for collecting system information?

**Hint:**
Look for services that are periodically executed and check their configurations for suspicious behavior.

**Answer:**
local-inventory.timer

---

### Validation
Each task is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and containing the Sofacy Fysbis backdoor, ensuring that students discover the required information through investigation rather than being given explicit details. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts present in the provided data.