# XMRig Cryptominer Investigation

## INFO_LEVEL
The IT department has received reports of unusually high CPU usage on several Linux servers in the network. Initial investigations suggest that one or more systems may be infected with cryptocurrency mining malware. Your task is to investigate these systems, identify the source of the high CPU usage, and determine if any systems have been compromised by cryptocurrency mining malware.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- `miner-host` (192.168.50.5)
- `second-host` (192.168.50.6)

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` system and identify any unauthorized or suspicious services running on the host.

**Hint:** Check the status of all services and look for any that appear unusual or out of place.

**Question:** What is the name of the suspicious service you identified?

## TRAINING_LEVEL 2
**Task:** On the `miner-host` system, identify the process responsible for the abnormal CPU or resource utilization.

**Hint:** Use process monitoring tools to identify processes consuming high CPU resources and investigate their properties.

**Question:** What is the name of the process responsible for the abnormal CPU usage?

## TRAINING_LEVEL 3
**Task:** Determine which network port is used for suspicious outbound communication from the `miner-host` system.

**Hint:** Investigate active network connections and look for any unusual or unexpected outbound connections.

**Question:** What is the port number used for the suspicious outbound communication?

## TRAINING_LEVEL 4
**Task:** Locate the executable or file associated with the suspicious activity on the `miner-host` system.

**Hint:** Correlate the suspicious process with files on disk and investigate any unusual or recently modified files.

**Question:** What is the filename or file path of the executable associated with the suspicious activity?

## TRAINING_LEVEL 5
**Task:** Identify the artifact responsible for installing or deploying the malicious software on the `miner-host` system.

**Hint:** Investigate installation artifacts and determine how the malware was introduced onto the system.

**Question:** What is the filename of the artifact responsible for installing the malicious software?

## TRAINING_LEVEL 6
**Task:** Determine the external host communicating with the `miner-host` system for suspicious outbound communication.

**Hint:** Analyze network connections and identify the destination IP address of the suspicious communication.

**Question:** What is the IP address of the external host communicating with the compromised system?

## TRAINING_LEVEL 7
**Task:** Identify the external service used by the `miner-host` system for cryptocurrency mining.

**Hint:** Analyze network traffic to identify the mining pool or command-and-control communication.

**Question:** What is the port number used for the mining pool communication?

## TRAINING_LEVEL 8
**Task:** Locate the configuration file used by the malicious software on the `miner-host` system.

**Hint:** Investigate malware artifacts to identify stored configuration information.

**Question:** What is the filename of the configuration file used by the malicious software?

## TRAINING_LEVEL 9
**Task:** Identify logs or artifacts created by the malicious software to record its activity on the `miner-host` system.

**Hint:** Discover hidden or unusual log files left by the malware.

**Question:** What is the filename of the log file created by the malicious software?

## TRAINING_LEVEL 10
**Task:** Determine how the malicious software is automatically started after reboot on the `miner-host` system through a system service.

**Hint:** Identify service-based persistence mechanisms.

**Question:** What is the name of the system service used for persistence?

## TRAINING_LEVEL 11
**Task:** Determine whether the malicious software uses scheduled execution for persistence on the `miner-host` system.

**Hint:** Identify scheduled task persistence mechanisms.

**Question:** What is the name of the scheduled task used for persistence?

## TRAINING_LEVEL 12
**Task:** Identify evidence showing how the malicious software was installed on the `miner-host` system.

**Hint:** Investigate logs, scripts, or artifacts revealing malware installation activity.

**Question:** What is the filename of the artifact providing evidence of the malware installation?

## TRAINING_LEVEL 13
**Task:** Identify scripts or tools used to propagate the malware to other systems from the `miner-host` system.

**Hint:** Analyze artifacts supporting malware propagation between hosts.

**Question:** What is the filename of the script or tool used for lateral movement?

## TRAINING_LEVEL 14
**Task:** Identify files or services used to transfer malware between systems from the `miner-host` system.

**Hint:** Correlate events across hosts to determine how malware was transferred.

**Question:** What is the name of the script or service used for file transfer?

## TRAINING_LEVEL 15
**Task:** Identify unauthorized remote access used to spread the malware from the `miner-host` system.

**Hint:** Investigate authentication and remote access logs to identify lateral movement.

**Question:** What is the destination host IP address used for unauthorized remote access?

## TRAINING_LEVEL 16
**Task:** Determine which additional system has been compromised through lateral movement from the `miner-host` system.

**Hint:** Correlate indicators across hosts to identify secondary infections.

**Question:** What is the IP address of the secondary compromised host?

## TRAINING_LEVEL 17
**Task:** Identify evidence demonstrating that the malware spread to additional hosts from the `miner-host` system.

**Hint:** Analyze logs and system artifacts to reconstruct propagation activity.

**Question:** What is the filename of the log file providing evidence of malware propagation?

## TRAINING_LEVEL 18
**Task:** Collect forensic evidence supporting the identified cryptomining activity on the `miner-host` system.

**Hint:** Gather relevant logs, process information, service configuration, persistence artifacts, and network evidence.

**Question:** What is the set of evidence collected to support the identified cryptomining activity?

## TRAINING_LEVEL 19
**Task:** Determine whether the observed activity on the `miner-host` system is malicious or benign and justify the conclusion.

**Hint:** Correlate collected evidence to classify the activity as unauthorized cryptomining or legitimate system behavior.

**Question:** What is the threat classification based on the collected evidence?

## TRAINING_LEVEL 20
**Task:** Block malicious outbound communication from the `miner-host` system while preserving legitimate network activity.

**Hint:** Apply firewall or network controls to contain the malware.

**Question:** What is the IP address or port number that was blocked to contain the malware?

## TRAINING_LEVEL 21
**Task:** Stop the malicious process or service responsible for the cryptomining activity on the `miner-host` system.

**Hint:** Safely terminate malicious execution while minimizing impact on legitimate services.

**Question:** What is the name of the process or service that was terminated?

## TRAINING_LEVEL 22
**Task:** Remove the service-based persistence mechanism used by the malware on the `miner-host` system.

**Hint:** Eliminate service persistence to prevent reinfection after reboot.

**Question:** What is the name of the service that was removed for persistence elimination?

## TRAINING_LEVEL 23
**Task:** Remove the scheduled task used to maintain persistence on the `miner-host` system.

**Hint:** Eliminate scheduled execution persistence mechanisms.

**Question:** What is the name of the scheduled task that was removed?

## TRAINING_LEVEL 24
**Task:** Remove the malicious executable and associated artifacts from the `miner-host` system.

**Hint:** Perform eradication while preserving relevant forensic evidence.

**Question:** What is the filename or file path of the malicious executable that was removed?

## TRAINING_LEVEL 25
**Task:** Identify evidence confirming compromise of the initially infected host, `miner-host`.

**Hint:** Verify compromise using forensic indicators collected from the host.

**Question:** What is the flag value confirming the compromise of the initially infected host?

## TRAINING_LEVEL 26
**Task:** Identify evidence confirming compromise of the laterally infected host, `second-host`.

**Hint:** Validate successful investigation of malware propagation across hosts.

**Question:** What is the flag value confirming the compromise of the laterally infected host?

## TRAINING_LEVEL 27
**Task:** Verify that the cryptominer has been successfully removed from the `miner-host` system and that no malicious processes, persistence mechanisms, or mining communications remain.

**Hint:** Validate the effectiveness of containment and eradication actions.

**Question:** What is the verification checklist or absence of expected indicators confirming successful removal of the cryptominer?