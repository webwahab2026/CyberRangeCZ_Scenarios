# Octopus-Rex Botnet Investigation

## INFO_LEVEL
The Octopus-Rex botnet is a multi-task botnet capable of various malicious activities including command and control (C2) communication, lateral movement, and data exfiltration. Your task is to investigate and respond to an Octopus-Rex botnet infection on the network.

## ACCESS_LEVEL
You have SSH access to the victim host `bot1` with the username `cyrano` and password `cyrano`. From there, you can investigate the network and connected hosts.

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service responsible for periodic external communication?

**Hint:** Check the systemd services and look for any unusual or unfamiliar services.

**Validation:** The correct answer is `bot-beacon.service`.

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service responsible for generating abnormal volumes of network traffic?

**Hint:** Look for services that might be related to network diagnostics or probes.

**Validation:** The correct answer is `bot-flood.service`.

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the timer unit that ensures the suspicious service is automatically started after reboot?

**Hint:** Check the systemd timers and look for any unusual or unfamiliar timers.

**Validation:** The correct answer is `bot-beacon.timer`.