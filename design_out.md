# Scenario: Linux/Rakos Backdoor Investigation

## INFO_LEVEL
The network has experienced unusual SSH activity and potential lateral movement between hosts. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have access to the `target` host with the username `cyrano` and password `cyrano`. From this host, you can investigate the network and connected systems.

## TRAINING_LEVEL 1
**Task:** Investigate the unusual SSH activity on the `target` host.
**Objective:** Identify and investigate the source of suspicious SSH connections.
**Hint:** Check the SSH logs and running processes for any anomalies.

## TRAINING_LEVEL 2
**Task:** Determine if the suspicious SSH activity is part of a larger lateral movement campaign.
**Objective:** Identify any file transfers or remote command executions that indicate lateral movement.
**Hint:** Examine the system logs and network connections for evidence of lateral movement.

## TRAINING_LEVEL 3
**Task:** Contain the threat by blocking the command-and-control (C2) communication.
**Objective:** Identify the C2 server and implement network controls to block its communication.
**Hint:** Analyze the network traffic and identify the destination IP address and port used for C2 communication.