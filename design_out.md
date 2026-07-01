### Scenario: Godfather Trojan Investigation

**INFO_LEVEL:**
The Godfather Android banking Trojan has been detected in your network. This trojan is designed to harvest login credentials for banking applications and other financial services, and drain the accounts. It uses web fakes to overlay on infected devices that appear when a user interacts with a decoy notification or tries to open one of the legitimate applications targeted by Godfather. Any data entered on the web fakes is exfiltrated to command-and-control (C&C) servers. Godfather can also exfiltrate SMS and push notifications to bypass two-factor authentication.

**ACCESS_LEVEL:**
You have access to the victim host `victim` with the username `cyrano` and password `cyrano`. You can also access the C2 server `c2-server` with the same credentials.

**TRAINING_LEVEL_1:**
**Task:** Identify the suspicious scheduled task/timer used by the Godfather trojan.
**Description:** Investigate the systemd timers on the victim host to find any suspicious scheduled tasks that might be related to the Godfather trojan.
**Hint:** Look for timers that are not part of the standard system configuration.
**Flag:** The name of the suspicious timer.

**TRAINING_LEVEL_2:**
**Task:** Identify the hidden malware directory used by the Godfather trojan.
**Description:** Search the victim host for any hidden directories that might be used by the Godfather trojan to store its files.
**Hint:** Look for directories with unusual names or locations.
**Flag:** The name of the hidden directory.

**TRAINING_LEVEL_3:**
**Task:** Identify the attacker-controlled C2 server.
**Description:** Investigate the network connections on the victim host to find any suspicious outbound connections to a command-and-control (C&C) server.
**Hint:** Look for connections to IP addresses that are not part of your internal network.
**Flag:** The IP address of the C2 server.