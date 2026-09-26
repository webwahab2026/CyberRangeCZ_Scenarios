# XMRig Cryptominer Investigation

## INFO_LEVEL
The IT department has received reports of unusually high CPU usage on several Linux servers in the network. Initial investigation suggests this might be caused by unauthorized cryptocurrency mining activity. Your task is to investigate these systems, identify the source of the problem, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- `miner-host` (192.168.50.5)
- `second-host` (192.168.50.6)

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` system and identify any unauthorized or suspicious services running.

**Hint:** Check the status of all running services and look for any that appear unusual or out of place.

**Validation:** The service name is `sys-monitor`.

## TRAINING_LEVEL 2
**Task:** On the `miner-host` system, identify the process responsible for the abnormal CPU or resource utilization.

**Hint:** Use process monitoring tools to analyze running processes and their resource consumption.

**Validation:** The process name is `sys-monitor`.

## TRAINING_LEVEL 3
**Task:** Locate the executable or file associated with the suspicious activity on the `miner-host` system.

**Hint:** Investigate the file system for any unusual or recently modified files that might be related to the suspicious process.

**Validation:** The filename is `/usr/local/sbin/xmrig`.

## TRAINING_LEVEL 4
**Task:** Identify the artifact responsible for installing or deploying the malicious software on the `miner-host` system.

**Hint:** Examine the user's command history and system logs for any evidence of recent installations or modifications.

**Validation:** The filename is `/tmp/.installer`.

## TRAINING_LEVEL 5
**Task:** Determine the external host communicating with the compromised `miner-host` system.

**Hint:** Analyze network connections and look for any suspicious outbound communication.

**Validation:** The IP address is `185.183.98.46`.

## TRAINING_LEVEL 6
**Task:** Determine which network port is used for suspicious outbound or inbound communication on the `miner-host` system.

**Hint:** Investigate network traffic and identify any abnormal communication ports.

**Validation:** The port number is `3333`.

## TRAINING_LEVEL 7
**Task:** Identify the external service used by the compromised `miner-host` system for cryptocurrency mining.

**Hint:** Analyze network traffic to identify mining pool or command-and-control communication.

**Validation:** The mining pool IP address and port number are `192.168.40.5:3333`.

## TRAINING_LEVEL 8
**Task:** Locate the configuration file used by the malicious software on the `miner-host` system.

**Hint:** Investigate malware artifacts to identify stored configuration information.

**Validation:** The filename is `/home/cyrano/.config/sys-monitor/config.json`.

## TRAINING_LEVEL 9
**Task:** Identify logs or artifacts created by the malicious software to record its activity on the `miner-host` system.

**Hint:** Discover hidden or unusual log files left by the malware.

**Validation:** The filename is `/var/log/.sys-mon`.

## TRAINING_LEVEL 10
**Task:** Determine how the malicious software is automatically started after reboot through a system service on the `miner-host` system.

**Hint:** Identify service-based persistence mechanisms.

**Validation:** The service name is `sys-monitor`.

## TRAINING_LEVEL 11
**Task:** Determine whether the malicious software uses scheduled execution for persistence on the `miner-host` system.

**Hint:** Identify scheduled task persistence mechanisms.

**Validation:** The scheduled task name is `sysupdate`.

## TRAINING_LEVEL 12
**Task:** Identify evidence showing how the malicious software was installed on the `miner-host` system.

**Hint:** Investigate logs, scripts, or artifacts revealing malware installation activity.

**Validation:** The filename is `/home/cyrano/.bash_history`.

## TRAINING_LEVEL 13
**Task:** Identify scripts or tools used to propagate the malware to other systems from the `miner-host` system.

**Hint:** Analyze artifacts supporting malware propagation between hosts.

**Validation:** The filename is `/usr/local/bin/sys-update.sh`.

## TRAINING_LEVEL 14
**Task:** Identify files or services used to transfer malware between systems from the `miner-host` system.

**Hint:** Correlate events across hosts to determine how malware was transferred.

**Validation:** The script name is `sys-update.sh`.

## TRAINING_LEVEL 15
**Task:** Identify unauthorized remote access used to spread the malware from the `miner-host` system.

**Hint:** Investigate authentication and remote access logs to identify lateral movement.

**Validation:** The destination host IP address is `192.168.50.6`.

## TRAINING_LEVEL 16
**Task:** Determine which additional system has been compromised through lateral movement from the `miner-host` system.

**Hint:** Correlate indicators across hosts to identify secondary infections.

**Validation:** The host IP address is `192.168.50.6`.

## TRAINING_LEVEL 17
**Task:** Identify evidence demonstrating that the malware spread to additional hosts from the `miner-host` system.

**Hint:** Analyze logs and system artifacts to reconstruct propagation activity.

**Validation:** The log filename is `/home/cyrano/sys-update.log`.

## TRAINING_LEVEL 18
**Task:** Collect forensic evidence supporting the identified cryptomining activity on the `miner-host` system.

**Hint:** Gather relevant logs, process information, service configuration, persistence artifacts, and network evidence.

**Validation:** The expected evidence set includes:
- Service name: `sys-monitor`
- Process name: `sys-monitor`
- Filename: `/usr/local/sbin/xmrig`
- Filename: `/tmp/.installer`
- IP address: `185.183.98.46`
- Port number: `3333`
- Mining pool IP address and port number: `192.168.40.5:3333`
- Filename: `/home/cyrano/.config/sys-monitor/config.json`
- Filename: `/var/log/.sys-mon`
- Service name: `sys-monitor`
- Scheduled task name: `sysupdate`
- Filename: `/home/cyrano/.bash_history`
- Filename: `/usr/local/bin/sys-update.sh`
- Script name: `sys-update.sh`
- Destination host IP address: `192.168.50.6`
- Host IP address: `192.168.50.6`
- Log filename: `/home/cyrano/sys-update.log`

## TRAINING_LEVEL 19
**Task:** Determine whether the observed activity is malicious or benign and justify the conclusion on the `miner-host` system.

**Hint:** Correlate collected evidence to classify the activity as unauthorized cryptomining or legitimate system behavior.

**Validation:** The threat classification is `malicious`.

## TRAINING_LEVEL 20
**Task:** Block malicious outbound communication while preserving legitimate network activity on the `miner-host` system.

**Hint:** Apply firewall or network controls to contain the malware.

**Validation:** The blocked IP address or blocked port is `185.183.98.46:3333`.

## TRAINING_LEVEL 21
**Task:** Stop the malicious process or service responsible for the cryptomining activity on the `miner-host` system.

**Hint:** Safely terminate malicious execution while minimizing impact on legitimate services.

**Validation:** The process name or service name is `sys-monitor`.

## TRAINING_LEVEL 22
**Task:** Remove the service-based persistence mechanism used by the malware on the `miner-host` system.

**Hint:** Eliminate service persistence to prevent reinfection after reboot.

**Validation:** The service name is `sys-monitor`.

## TRAINING_LEVEL 23
**Task:** Remove the scheduled task used to maintain persistence on the `miner-host` system.

**Hint:** Eliminate scheduled execution persistence mechanisms.

**Validation:** The scheduled task name is `sysupdate`.

## TRAINING_LEVEL 24
**Task:** Remove the malicious executable and associated artifacts from the compromised `miner-host` system.

**Hint:** Perform eradication while preserving relevant forensic evidence.

**Validation:** The filename or file path is `/usr/local/sbin/xmrig`.

## TRAINING_LEVEL 25
**Task:** Identify evidence confirming compromise of the initially infected host `miner-host`.

**Hint:** Verify compromise using forensic indicators collected from the host.

**Validation:** The flag value is `miner-host_compromised`.

## TRAINING_LEVEL 26
**Task:** Identify evidence confirming compromise of the laterally infected host `second-host`.

**Hint:** Validate successful investigation of malware propagation across hosts.

**Validation:** The flag value is `second-host_compromised`.

## TRAINING_LEVEL 27
**Task:** Verify that the cryptominer has been successfully removed and that no malicious processes, persistence mechanisms, or mining communications remain on the `miner-host` system.

**Hint:** Validate the effectiveness of containment and eradication actions.

**Validation:** The verification checklist or absence of expected indicators includes:
- No service named `sys-monitor` is running.
- No process named `sys-monitor` is running.
- The file `/usr/local/sbin/xmrig` has been removed.
- The file `/tmp/.installer` has been removed.
- No outbound communication to `185.183.98.46:3333` is present.
- The service-based persistence mechanism has been removed.
- The scheduled task `sysupdate` has been removed.
- The malicious executable and associated artifacts have been removed.