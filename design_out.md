# Pulse Secure RADIALPULSE Trojan Investigation

## INFO_LEVEL
The victim host in your network has been compromised by the RADIALPULSE trojan, which targets Pulse Secure VPN devices. This malware bypasses authentication, persists across upgrades, and maintains access through webshells. Your task is to investigate the compromised host, identify the malware's persistence mechanisms, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim
- IP Address: 192.168.60.10
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for unauthorized or suspicious services running on the system.
**Objective:** Enumerate running services and distinguish legitimate services from trojan-related services.
**Hint:** Check the status of all services and look for any that appear unusual or out of place.

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing the malware.
**Objective:** Identify scheduled execution persistence mechanisms (e.g., cron, systemd timers, Windows Scheduled Tasks).
**Hint:** Examine the systemd timers and services to find any that might be related to the malware.

## TRAINING_LEVEL 3
**Task:** Locate files installed by the malware on the compromised host.
**Objective:** Correlate suspicious activity with files introduced by the trojan.
**Hint:** Search for hidden directories and files that might contain malware components or collected data.

---

**Validation:**
1. **TRAINING_LEVEL 1:** The student must identify the suspicious service related to the trojan.
2. **TRAINING_LEVEL 2:** The student must determine the scheduled task or timer responsible for executing the malware.
3. **TRAINING_LEVEL 3:** The student must locate the files installed by the malware on the compromised host.

This scenario aligns with the provided MISP event, security profile, topology, and Ansible configuration, ensuring a realistic and challenging investigation exercise.