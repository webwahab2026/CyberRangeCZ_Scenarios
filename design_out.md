# Hajime Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential security incidents. Your task is to investigate and identify any malicious activity, determine its scope, and recommend containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host `victim` with the username `ubuntu` and password `ubuntu`. From there, you can investigate the network and connected devices.

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is periodically communicating with an external host?

**Hint:** Check the systemd services and look for any unusual or recently created services.

**Validation:** The correct answer is `bot-beacon.service`.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service that is generating abnormal volumes of network traffic?

**Hint:** Look for services that are not standard system services and check their configuration files.

**Validation:** The correct answer is `bot-flood.service`.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Investigate the systemd timers and services to find how the service is scheduled to run.

**Validation:** The correct answer is `system-update-checker.timer`.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Hajime botnet activity, identifying suspicious services, and understanding their persistence mechanisms. The scenario adheres to the sandbox constraints and uses only the indicators and services present in the provided data.