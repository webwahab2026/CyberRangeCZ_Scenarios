# Rhombus Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and respond to these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that communicates with an external host?

**Hint:** Check the systemd services and look for unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd timers and services related to the suspicious service identified in the previous task.

## TRAINING_LEVEL 3
**Task:** Determine the external host communicating with the compromised system.

**Question:** What is the IP address of the command-and-control server?

**Hint:** Examine the network connections and logs of the suspicious service to identify the external host.