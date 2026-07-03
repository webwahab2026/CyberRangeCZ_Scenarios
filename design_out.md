Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario Name:** Kobalos Malware Investigation

**Objective:** Investigate and respond to a Kobalos malware infection in a high-performance computing environment.

**Difficulty Level:** Intermediate

**Cybersecurity Approach:** Defence-oriented

**Scenario Type:** Exercise

**Include Q/A:** true

**Include Hint:** true

---

**INFO_LEVEL:**

1. You are a cybersecurity analyst working for a high-performance computing (HPC) organization.
2. Your organization has detected suspicious network activity and believes a Kobalos malware infection may be present.
3. Kobalos is a complex, multiplatform malware that targets HPC clusters and other high-profile systems.
4. Your task is to investigate the infection, identify indicators of compromise, and contain the threat.

---

**ACCESS_LEVEL:**

1. Entry host: target (IP: 192.168.50.5)
2. Username: cyrano
3. Password: cyrano
4. Access method: SSH
5. Privilege boundaries: You have sudo privileges on the entry host.

---

**TRAINING_LEVEL 1:**

**Task:** Identify and investigate suspicious outbound connections.

**Description:**
1. Investigate the network connections on the target host.
2. Identify any suspicious outbound connections.
3. Determine the destination IP address, port, and frequency of the connections.

**Hint:** Check the system logs and network statistics for unusual outbound traffic.

**Q/A:**
Q: What is the destination IP address of the suspicious outbound connections?
A: 192.168.40.5

**Flag:** 192.168.40.5

---

**TRAINING_LEVEL 2:**

**Task:** Investigate and contain the suspicious service.

**Description:**
1. Identify the service responsible for the suspicious outbound connections.
2. Investigate the service's configuration and behavior.
3. Contain the service by stopping it and preventing it from starting at boot.

**Hint:** Check the systemd services and look for any unusual or recently created services.

**Q/A:**
Q: What is the name of the suspicious service?
A: lab-checkin.timer

**Flag:** lab-checkin.timer

---

**TRAINING_LEVEL 3:**

**Task:** Investigate and remove the persistence mechanism.

**Description:**
1. Investigate the persistence mechanism used by the malware.
2. Identify any scheduled tasks or cron jobs that ensure the malware's persistence.
3. Remove the persistence mechanism to prevent the malware from restarting after a reboot.

**Hint:** Check the systemd timers and look for any unusual or recently created timers.

**Q/A:**
Q: What is the name of the persistence mechanism?
A: lab-checkin.timer

**Flag:** lab-checkin.timer

---

**Scenario Validation:**

1. The scenario is strictly aligned with the provided MISP event, focusing on the Kobalos malware and its behavior.
2. All tasks reference real hosts, services, and file paths from the topology and Ansible configuration.
3. The scenario uses only indicators explicitly present in the MISP event for threat intelligence elements.
4. The scenario follows the NICE Incident Response profile, focusing on investigating, analyzing, and responding to network cybersecurity incidents.
5. The scenario includes three TRAINING_LEVEL tasks, each with a clear objective, description, hint, Q/A, and flag.

---

**Sandbox Analysis:**

1. **Host Inventory:**
   - c2-server (192.168.40.5)
   - target (192.168.50.5)
   - next-target (192.168.50.6)
   - router (192.168.40.1, 192.168.50.1)

2. **Service Map:**
   - SSH (port 22) on all hosts
   - lab-checkin.timer and lab-checkin.service on target
   - payload-transfer.service and payload-transfer.timer on target
   - local-inventory.service and local-inventory.timer on target

3. **File and Artifact Map:**
   - /home/cyrano/.ssh on all hosts
   - /var/log/lab-checkin.log on target
   - /var/log/local-inventory/inventory.log on target
   - /usr/local/bin/lab-checkin.sh on target
   - /usr/local/bin/payload-transfer.sh on target

4. **Access Model:**
   - Entry host: target (192.168.50.5)
   - Username: cyrano
   - Password: cyrano
   - Access method: SSH
   - Privilege boundaries: sudo privileges on the entry host

5. **Attack Surface:**
   - Network connections and services on the target host
   - Systemd services and timers on the target host
   - SSH keys and known hosts on all hosts
   - File transfers and lateral movement between target and next-target

---

This scenario provides a realistic and challenging exercise for intermediate-level cybersecurity analysts, focusing on investigating and responding to a Kobalos malware infection in an HPC environment. The scenario is strictly aligned with the provided MISP event, topology, Ansible configuration, and security profile.