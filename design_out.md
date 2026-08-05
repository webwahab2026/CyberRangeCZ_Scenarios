### Scenario: PACHA Backdoor Investigation

**INFO_LEVEL:**
The PACHA backdoor malware has been detected in your network. This malware is known to infect Linux servers and deploy coinminers. It uses various scripts to download and execute payloads from different URLs. The malware also includes iptables rules and other network activity indicators. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can access other hosts in the network.

**TRAINING_LEVEL 1:**
**Task:** Identify and investigate an unauthorized or suspicious service running on the `target` host.
**Question:** What is the name of the suspicious service running on the `target` host?
**Hint:** Check the running services and look for any that seem unusual or unauthorized.
**Answer:** sh.service

**TRAINING_LEVEL 2:**
**Task:** Determine how the suspicious service is automatically started after reboot.
**Question:** What is the persistence mechanism used by the suspicious service?
**Hint:** Investigate systemd services and timers to find how the service is started automatically.
**Answer:** systemd timer

**TRAINING_LEVEL 3:**
**Task:** Identify file transfers or remote execution used to move between hosts.
**Question:** What is the name of the script responsible for lateral movement from the `target` host to the `next-target` host?
**Hint:** Look for scripts and services that handle file transfers or remote execution.
**Answer:** payload-transfer.sh