# Linux.Ngioweb Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns, with multiple systems generating excessive outbound connections. Initial analysis suggests potential botnet activity. Your task is to investigate and contain this activity.

## ACCESS_LEVEL
You have SSH access to the victim host `victim` with credentials:
- Username: ubuntu
- Password: ubuntu

From this host, you can access other systems in the network as needed.

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external command-and-control server?

**Hint:** Check running services and look for unusual network connections.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating excessive network traffic?

**Hint:** Examine systemd timers and services for unusual activity.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd timers and services that start automatically.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging investigation exercise.