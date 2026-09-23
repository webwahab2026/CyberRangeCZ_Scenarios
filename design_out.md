# Scenario: Linux/Remaiten Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and potential unauthorized access. Your task is to investigate and identify any malicious activity, determine its scope, and recommend containment measures.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Host: victim (192.168.80.100)
- Username: ubuntu
- Password: ubuntu

## TRAINING_LEVEL 1
**Task:** Investigate the unusual traffic patterns on the victim host.

**Question:** What service is responsible for generating abnormal volumes of network traffic?

**Hint:** Check the running services and look for any unusual or unfamiliar services.

**Validation:** The correct service name is "bot-flood.service".

## TRAINING_LEVEL 2
**Task:** Determine the target of the abnormal network traffic.

**Question:** What is the IP address of the system receiving the abnormal volume of network traffic?

**Hint:** Examine the network connections and logs related to the suspicious service.

**Validation:** The correct IP address is "192.168.80.100".

## TRAINING_LEVEL 3
**Task:** Investigate the persistence mechanism of the suspicious service.

**Question:** How is the suspicious service automatically started after a reboot?

**Hint:** Look for systemd timers or other scheduling mechanisms that might be responsible for starting the service.

**Validation:** The correct persistence mechanism is "systemd timer".

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating and containing the Linux/Remaiten botnet activity, with a defense-oriented approach suitable for an intermediate difficulty level. The scenario includes questions, hints, and validation criteria to guide and assess the students' investigation process.