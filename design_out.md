# Sednit Dropper Investigation

## INFO_LEVEL
The Sednit group is known for using sophisticated malware toolkits designed for espionage and long-term monitoring of targeted systems. One of their tools, Seduploader, is a dropper used to deliver other malicious payloads such as Xagent and Xtunnel. Your task is to investigate a compromised system to identify and analyze the Sednit dropper and its associated artifacts.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service running on the compromised host.

**Question:** What is the name of the suspicious service that was installed on the system?

**Hint:** Check the systemd service files in the /etc/systemd/system directory for any unusual or recently created services.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity.

**Question:** What is the name of the timer responsible for the periodic execution of the suspicious service?

**Hint:** Look for timer files in the /etc/systemd/system directory that correspond to the suspicious service identified in the previous task.

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the system by the malicious software.

**Question:** What is the name of the directory created to conceal malicious files or payloads?

**Hint:** Investigate unusual or hidden directories, especially those created around the time of the suspected compromise.

---

**Validation:**

The scenario strictly adheres to the provided MISP event, sandbox topology, and Ansible configuration. All tasks are aligned with the Sednit dropper's behavior and the available infrastructure. The tasks encourage investigation and correlation of artifacts across the victim host, staging server, and C2 server, ensuring a comprehensive understanding of the attack chain. The hidden flags are derived from the sandbox's actual configuration, and the tasks do not reveal any implementation details explicitly.