# KrustyLoader Investigation

## INFO_LEVEL
KrustyLoader is a Rust-based malware linked to Ivanti ConnectSecure compromises. It is designed to download and execute a Sliver backdoor. The malware shares almost 100% code similarity among its samples and is used to exploit zero-day vulnerabilities in Ivanti Connect Secure VPN product.

## ACCESS_LEVEL
You have been granted access to the victim host in the network. Your credentials are:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the victim host for any unauthorized or suspicious services running on the system.

**Objective:** Enumerate running services and distinguish legitimate services from malicious ones.

**Hint:** Check the status of all services and look for any that appear unusual or unauthorized.

**Flag:** [Service name]

## TRAINING_LEVEL 2
**Task:** Determine whether a scheduled task or timer is responsible for automatically executing suspicious activity on the victim host.

**Objective:** Identify scheduled execution persistence mechanisms (e.g., cron, systemd timers, Windows Scheduled Tasks).

**Hint:** Examine the systemd timers and services to find any that might be related to the suspicious activity.

**Flag:** [Timer or task name]

## TRAINING_LEVEL 3
**Task:** Locate files introduced onto the victim system by the malicious software.

**Objective:** Correlate suspicious activity with newly created files and identify malware artifacts.

**Hint:** Investigate the /tmp/.session directory for any suspicious files.

**Flag:** [Filename]