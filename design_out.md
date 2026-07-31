# Linux/NyaDrop Incident Response Scenario

## INFO_LEVEL
The victim host in your network has exhibited unusual behavior, including unexpected network connections and suspicious file modifications. Your task is to investigate and respond to this potential security incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services.

**Question:** What is the name of the suspicious service running on the victim host?

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

## TRAINING_LEVEL 2
**Task:** Determine if any scheduled tasks or timers are responsible for automatically executing suspicious activity.

**Question:** What is the name of the timer responsible for the suspicious activity?

**Hint:** Investigate the systemd timers and look for any that might be related to the suspicious service.

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Question:** What is the name of the directory created to conceal malicious files or payloads?

**Hint:** Search for hidden or unusual directories that might contain suspicious files.

## Answer Section
1. **Answer:** nyadrop.timer
2. **Answer:** /tmp/.session
3. **Answer:** /tmp/.session/rat.sh