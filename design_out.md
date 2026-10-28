# KrustyLoader Incident Response Scenario

## INFO_LEVEL
KrustyLoader is a Rust-based malware linked to Ivanti ConnectSecure compromises. It is designed to download and execute a Sliver backdoor. The malware exploits vulnerabilities CVE-2024-21887 and CVE-2023-46805 to achieve unauthenticated remote code execution.

## ACCESS_LEVEL
You are an incident responder with access to the victim host `victim` (IP: 192.168.120.10) using the credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate Suspicious Scheduled Task
**Description:** While reviewing the victim host, you notice unusual system behavior. Investigate the scheduled tasks or timers to identify any suspicious or unauthorized execution mechanisms.
**Hint:** Check systemd timers and services for any unusual entries.
**Flag:** [Timer or task name]

## TRAINING_LEVEL 2
**Task:** Analyze Suspicious Dropped Files
**Description:** Examine the victim host for any files that appear to have been introduced by malicious software. Focus on directories that may have been created to conceal malicious files or payloads.
**Hint:** Look for recently created directories and files, especially those in unusual locations.
**Flag:** [Filename]

## TRAINING_LEVEL 3
**Task:** Identify Remote Access Component
**Description:** Determine if there is a component responsible for establishing unauthorized remote access on the victim host. Analyze any scripts or executables that might be used for this purpose.
**Hint:** Investigate scripts in suspicious directories and check their contents for remote access functionality.
**Flag:** [Script name]

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a KrustyLoader compromise, focusing on identifying and analyzing suspicious services, dropped files, and remote access components. The flags are hidden to encourage thorough investigation and discovery.