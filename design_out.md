Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**INFO_LEVEL**
- **Scenario Title**: Rhombus Botnet Investigation
- **Scenario Description**: Investigate and respond to a Rhombus Linux DDoS botnet infection affecting your network. The botnet targets VPS and IoT devices, communicates with C2 servers, and performs DDoS attacks.
- **Prerequisites**: Basic Linux command line knowledge, familiarity with network services and security tools.
- **Learning Objectives**:
  - Identify and investigate suspicious services and network connections.
  - Analyze persistence mechanisms.
  - Contain and mitigate botnet activities.

**ACCESS_LEVEL**
- **Entry Host**: bot1 (IP: 192.168.70.10)
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH (Port 22)

---

**TRAINING_LEVEL 1**
- **Task Title**: Identify Suspicious Beacon Service
- **Task Description**: Investigate the system services on bot1 and identify the suspicious beacon service used by the Rhombus botnet.
- **Hint**: Look for services related to system health or updates that might be unusual.
- **Flag**: bot-beacon-rc.local.timer

**Validation**:
- The user must find and report the name of the suspicious beacon service.

---

**TRAINING_LEVEL 2**
- **Task Title**: Identify C2 Communication
- **Task Description**: Analyze network connections from bot1 to identify the command-and-control (C2) server communication. Determine the IP address and port used for this communication.
- **Hint**: Check active network connections and listen ports.
- **Flag**: 192.168.70.5:2222

**Validation**:
- The user must identify and report the C2 server IP address and port.

---

**TRAINING_LEVEL 3**
- **Task Title**: Contain C2 Communication
- **Task Description**: Implement measures to contain the C2 communication. Block the identified port on bot1 to prevent further communication with the C2 server.
- **Hint**: Use firewall rules to block the specific port.
- **Flag**: 2222

**Validation**:
- The user must block the identified C2 port and provide evidence of the blocking action.

---

**Debriefing**
- **Scenario Summary**: You have successfully investigated and contained the Rhombus botnet infection on bot1. By identifying the suspicious beacon service, analyzing C2 communication, and implementing containment measures, you have mitigated the immediate threat.
- **Key Takeaways**:
  - Regularly monitor system services for unusual or suspicious activities.
  - Analyze network connections to identify and block C2 communications.
  - Implement containment measures to prevent further compromise.

---

This scenario aligns with the provided MISP event, security profile, and sandbox environment, ensuring a realistic and educational experience for participants.