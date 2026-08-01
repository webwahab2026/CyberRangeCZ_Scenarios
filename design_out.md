# Hajime Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and identify any malicious activity, determine its scope, and recommend containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host `victim` with the username `ubuntu` and password `ubuntu`. From there, you can investigate the network and connected devices.

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external host?

**Hint:** Check running services and look for any unusual network connections or periodic activities.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service generating excessive network traffic?

**Hint:** Examine network connections and look for services that are sending a high volume of packets to a specific destination.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate systemd services and timers to find how the service is scheduled to run periodically.

---

### Scenario Notes

1. **Sandbox Analysis**:
   - **Host Inventory**:
     - `c2-server`: Ubuntu, role as C2 server.
     - `bot1`: Ubuntu, role as bot.
     - `bot2`: Ubuntu, role as bot.
     - `victim`: Ubuntu, role as victim.
   - **Service Map**:
     - `c2-server`: Running a C2 listener on port 2222.
     - `bot1` and `bot2`: Running beacon and flood services.
   - **File and Artifact Map**:
     - Beacon scripts and logs in `/usr/local/lib/.botcache` and `/var/lib/.botcache`.
     - Flood scripts and logs in the same directories.
   - **Access Model**:
     - Entry host: `victim` with credentials `ubuntu:ubuntu`.
     - From `victim`, you can investigate `bot1` and `bot2` via SSH using the `cyrano:cyrano` credentials.
   - **Attack Surface**:
     - Investigate services, logs, and network connections on `bot1` and `bot2`.

2. **MISP Alignment**:
   - The scenario focuses on the Hajime botnet behavior, including beaconing and flooding activities, as described in the MISP event.

3. **Training Level Examples Usage**:
   - Tasks are designed to guide students through discovering the required information through investigation, aligning with the provided examples but not copying them verbatim.

This scenario ensures that all tasks are consistent with the sandbox environment and MISP event, providing a realistic and challenging investigation exercise.