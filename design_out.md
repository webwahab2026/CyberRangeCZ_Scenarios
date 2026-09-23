Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**INFO_LEVEL**
The Sednit group, also known as APT28, Fancy Bear, and Sofacy, is a group of attackers operating since 2004. Their main objective is to steal confidential information from specific targets. The group developed two different spying backdoors for long-term monitoring, named Sedreco and Xagent, to maximize the chance of avoiding detection. The Xagent backdoor can communicate with its C&C server over email with a custom protocol, which in some cases is based on Georgian words. The Sednit group also developed a network proxy tool, named Xtunnel, to transform a compromised computer into a network pivot, allowing contact with machines normally unreachable from the Internet.

**ACCESS_LEVEL**
You have been given access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

You can access this host via SSH on port 22.

**TRAINING_LEVEL 1**
**Task:** Suspicious Network Activity Investigation
**Description:** While monitoring network traffic, you've noticed unusual outbound connections from the target host. Investigate this activity and identify the service responsible for these connections.
**Hint:** Check the systemd services and look for any unusual or unfamiliar services.
**Validation:** The service name is bkd.service

**TRAINING_LEVEL 2**
**Task:** Persistence Mechanism Discovery
**Description:** Now that you've identified the suspicious service, determine how it maintains persistence on the system. Find out how this service is automatically started after a system reboot.
**Hint:** Examine the systemd unit files and timers related to the suspicious service.
**Validation:** The persistence mechanism is lab-checkin.timer

**TRAINING_LEVEL 3**
**Task:** Lateral Movement Investigation
**Description:** Investigate if the suspicious activity on the target host has led to any lateral movement within the network. Check for any file transfers or remote execution attempts to other hosts.
**Hint:** Examine the systemd services and logs related to file transfers or remote execution.
**Validation:** The service name is payload-transfer.service

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. The tasks are designed to guide students through the investigation of a Sednit/Xagent-related incident, focusing on service discovery, persistence mechanism identification, and lateral movement investigation. The scenario uses only the hosts, services, and artifacts present in the sandbox, and all indicators are taken from the MISP event. The tasks follow the structure and style of the provided training level examples while maintaining alignment with the sandbox reality.