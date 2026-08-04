# Scenario: Mirai Botnet Investigation

## INFO_LEVEL
The network has experienced unusual traffic patterns and performance degradation. Your task is to investigate and identify the source of these issues.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Question:** What is the name of the suspicious service that is beaconing to an external host?

**Hint:** Check the systemd services and look for any unusual or recently created services.

**Validation:** The correct answer is "bot-beacon.service".

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Question:** What is the name of the service that is generating the abnormal network traffic?

**Hint:** Look for services that are scheduled to run periodically and generate network traffic.

**Validation:** The correct answer is "bot-flood.service".

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the name of the timer unit that ensures the suspicious service starts automatically after reboot?

**Hint:** Investigate the systemd timers to find the one associated with the suspicious service.

**Validation:** The correct answer is "bot-beacon.timer".