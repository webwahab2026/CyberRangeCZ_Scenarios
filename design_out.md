# Rhombus Botnet Incident Response Scenario

## INFO_LEVEL

This scenario involves investigating a Linux-based Rhombus botnet infection on a network. The botnet has established persistence mechanisms and is communicating with a Command and Control (C2) server. The malware uses IRC protocol for C2 communication and performs DDoS attacks. The sandbox environment contains a C2 server and two infected bots (bot1 and bot2) that are actively communicating with the C2 server and performing simulated DDoS floods against a victim host.

## ACCESS_LEVEL

Access to the environment is provided through SSH with the username `cyrano` and password `cyrano` on the following hosts:
- bot1 (192.168.70.10)
- bot2 (192.168.70.11)
- c2-server (192.168.70.5)

The victim host (192.168.80.100) is not directly accessible for SSH access but is the target of the DDoS attacks.

## TRAINING_LEVEL

### Task 1: Identify the C2 Communication Mechanism

**Task Description:**  
Investigate the bot hosts to identify how the Rhombus botnet communicates with its Command and Control (C2) server. Determine the specific service or script responsible for sending beacon signals to the C2 server.

**Instructions:**  
1. SSH into either bot1 or bot2 using the credentials `cyrano`/`cyrano`
2. Examine running services and scheduled tasks to identify beacon-related processes
3. Review log files for evidence of C2 communication
4. Identify the specific service name responsible for beaconing

**Validation:**  
The task is complete when you identify the beacon service name. The flag is the name of the systemd service responsible for sending beacon signals to the C2 server.

**Hint:**  
Look for services that run on a schedule and contain references to C2 communication or beaconing.

### Task 2: Identify Persistence Mechanisms

**Task Description:**  
Investigate the bot hosts to identify how the Rhombus botnet maintains persistence on the infected systems. Determine the specific service or script responsible for ensuring the malware survives system reboots.

**Instructions:**  
1. SSH into either bot1 or bot2 using the credentials `cyrano`/`cyrano`
2. Examine system startup mechanisms and scheduled tasks
3. Look for scripts or services that are configured to run at boot or on a regular schedule
4. Identify the specific service name responsible for persistence

**Validation:**  
The task is complete when you identify the persistence service name. The flag is the name of the systemd service responsible for maintaining persistence on the infected host.

**Hint:**  
Persistence mechanisms often involve systemd timers or scripts added to system startup files like rc.local.

### Task 3: Identify the DDoS Attack Vector

**Task Description:**  
Investigate the bot hosts to identify how the Rhombus botnet performs DDoS attacks. Determine the specific service or script responsible for sending flood traffic to the victim host.

**Instructions:**  
1. SSH into either bot1 or bot2 using the credentials `cyrano`/`cyrano`
2. Examine running services and scheduled tasks to identify flood-related processes
3. Review log files for evidence of DDoS attack activity
4. Identify the specific service name responsible for sending flood traffic

**Validation:**  
The task is complete when you identify the flood service name. The flag is the name of the systemd service responsible for sending DDoS flood traffic to the victim host.

**Hint:**  
Look for services that run on a schedule and contain references to network flooding or DDoS attacks.