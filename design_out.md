Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
**Scenario Title:** Sofacy Fysbis Backdoor Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential compromise involving the Sofacy group's Fysbis Linux backdoor. The backdoor is known to establish command and control (C2) communication and exfiltrate data. Your mission is to investigate the compromised hosts, identify the malicious activity, and contain the threat.

**Scenario Learning Objectives:**
- Identify and investigate suspicious services and processes
- Analyze network communication for signs of C2 activity
- Investigate lateral movement techniques
- Contain and eradicate the threat

**Scenario Difficulty:** Intermediate

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

**ACCESS_LEVEL**
**Entry Host:** target (IP: 192.168.50.5)
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

**Additional Hosts:**
- next-target (IP: 192.168.50.6)
- c2-server (IP: 192.168.40.5)

---

**TRAINING_LEVEL 1**
**Task Title:** Suspicious Service Discovery

**Task Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host and identify any suspicious or unauthorized services.

**Learning Objective:**
Enumerate running services and distinguish legitimate from suspicious services.

**Hint:**
Check the status of all running services and look for any that seem out of place or unfamiliar.

**Q/A:**
What is the name of the suspicious service running on the target host?

---

**TRAINING_LEVEL 2**
**Task Title:** C2 Communication Discovery (Port)

**Task Description:**
Now that you've identified the suspicious service, investigate its network activity. Determine which network port is used for the suspicious communication.

**Learning Objective:**
Investigate network traffic and identify suspicious ports.

**Hint:**
Examine the network connections associated with the suspicious service.

**Q/A:**
Which network port is used for the suspicious communication?

---

**TRAINING_LEVEL 3**
**Task Title:** Lateral Movement Investigation

**Task Title:** Lateral Movement Investigation

**Task Description:**
Investigate if the attacker has moved laterally from the target host to other hosts in the network. Look for evidence of file transfers or remote execution.

**Learning Objective:**
Correlate events across hosts to identify attacker lateral movement.

**Hint:**
Check for any scripts or services that transfer files between hosts.

**Q/A:**
What is the name of the script or service used for lateral movement?

---

**Scenario Validation:**
To validate the scenario, ensure that:
1. The suspicious service (systemkernelservicedefender.service) is running on the target host.
2. The service is listening on port 80 for C2 communication.
3. The payload-transfer.sh script is used for lateral movement between target and next-target hosts.
4. The tasks are aligned with the learning objectives and the provided training level examples.

**Scenario Notes:**
- The scenario is designed to be feasible within the provided sandbox environment.
- All indicators, hosts, services, and file paths are derived from the topology and Ansible configuration.
- The scenario focuses on investigation and containment tasks relevant to the Sofacy Fysbis backdoor.

This scenario provides a realistic and engaging exercise for incident responders to investigate and contain a Linux backdoor threat. The tasks are designed to align with the NICE Incident Response profile and the provided training level examples.