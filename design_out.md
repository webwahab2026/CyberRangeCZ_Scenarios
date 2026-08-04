# NyaDrop Incident Response Scenario

## INFO_LEVEL
The target network has been compromised by the Linux/NyaDrop backdoor malware. This malware targets MIPS-based IoT devices and opens an internet socket to remotely connect to a remote host for receiving data of any Linux executable stream intended to infect the compromised machine. The received data is saved as 'nya' ELF malware file and then executed by Linux/NyaDrop with its permission privilege on the targeted MIPS CPU architecture device. The 'nya' dropped file is deleted every time the next new attacks are successfully logged in to the MIPS machine and then updating the previously saved 'nya' malware.

Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Hostname: target
- Username: cyrano
- Password: cyrano

From the target host, you can SSH to the next-target host using the same credentials.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for any suspicious services or processes.

**Question:** What is the name of the suspicious service running on the target host?

**Hint:** Check the systemd services and look for any unfamiliar or suspicious services.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is automatically started after reboot.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine the systemd service files and timers to identify how the service is set to start automatically.

## TRAINING_LEVEL 3
**Task:** Identify the file associated with the suspicious activity.

**Question:** What is the name of the file associated with the suspicious service?

**Hint:** Look for files in the home directory of the user that might be related to the suspicious service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation and response process while adhering to the constraints and requirements specified.