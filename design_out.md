Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. Here's the scenario:

---

**Scenario Title:** Hajime Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a compromised Linux IoT device infected with the Hajime botnet. Your goal is to identify and contain the malicious activity while preserving evidence for further analysis.

**INFO_LEVEL:**
The Hajime botnet is a peer-to-peer (P2P) botnet that targets Linux IoT devices. It spreads by exploiting default or weak credentials and then establishes a P2P network for communication and command and control (C2). The botnet is known for its persistence mechanisms and ability to maintain a presence on infected devices.

**ACCESS_LEVEL:**
You have SSH access to the compromised host `bot1` with the username `cyrano` and password `cyrano`. You can also access the C2 server `c2-server` with the same credentials.

**TRAINING_LEVEL 1:**
**Task:** Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for sending beacon periodically to the C2 Server.

**Step-by-step solution:**
1. Connect to the compromised host `bot1` using SSH with the provided credentials.
2. List all services, including inactive ones, using the command `systemctl list-units --type=service --all`.
3. Look for unfamiliar service names or misspellings of legitimate services.
4. Identify the service responsible for sending beacon to the C2 server.

**Hint 1:** Use `systemctl list-units --type=service --all` to list all services.
**Hint 2:** Look for services with unusual descriptions or startup behavior.
**Hint 3:** The service name is the hidden flag.

**TRAINING_LEVEL 2:**
**Task:** An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.

**Step-by-step solution:**
1. From the previous task, you have identified the service responsible for sending beacon to the C2 server.
2. Inspect the service configuration using the command `systemctl cat <service>`.
3. Pay particular attention to the `ExecStart` line, which specifies the path of the script launched by the service.
4. Check the script to find the communication port with the C2 server.

**Hint 1:** Use `systemctl cat <service>` to inspect the service configuration.
**Hint 2:** Look for the `ExecStart` line in the service configuration.
**Hint 3:** The communication port is the hidden flag.

**TRAINING_LEVEL 3:**
**Task:** Investigators suspect how the C2 beacon service automatically resumes after the system starts and continues to execute periodically. Determine which system component is responsible for scheduling this activity.

**Step-by-step solution:**
1. List all timers using the command `systemctl list-timers --all`.
2. Look for timers associated with the service identified in the previous tasks.
3. Inspect the timer configuration using the command `systemctl cat <timer>`.
4. Identify the timer responsible for scheduling the C2 beacon service.

**Hint 1:** Use `systemctl list-timers --all` to list all timers.
**Hint 2:** Look for timers associated with the service identified in the previous tasks.
**Hint 3:** The timer name is the hidden flag.

---

This scenario is strictly aligned with the provided sandbox environment, MISP event, and security profile. It focuses on the investigation and containment of the Hajime botnet, with tasks designed to help students develop their incident response skills. The scenario includes three training level tasks, each with a step-by-step solution and hints to guide students through the investigation process.