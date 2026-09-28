# CoinMiner Investigation Scenario

## INFO_LEVEL
The IT department has received reports of unusually high CPU usage on several Linux servers in the network. Initial checks suggest this might be caused by unauthorized cryptocurrency mining activity. Your task is to investigate these systems, identify the source of the problem, and contain the threat.

## ACCESS_LEVEL
You have SSH access to the following systems with the username `cyrano` and password `cyrano`:
- `miner-host` (192.168.50.5)
- `second-host` (192.168.50.6)

## TRAINING_LEVEL 1
**Task:** Investigate the `miner-host` system and identify any unauthorized or suspicious services running.

**Hint:** Check the status of all system services and look for any that appear unusual or out of place.

**Validation:** The correct answer is `sh.service`.

## TRAINING_LEVEL 2
**Task:** On the `miner-host` system, identify the process responsible for the abnormal CPU or resource utilization.

**Hint:** Use process monitoring tools to examine running processes and their resource consumption.

**Validation:** The correct answer is `sh`.

## TRAINING_LEVEL 3
**Task:** Determine which network port is used for suspicious outbound communication from the `miner-host` system.

**Hint:** Investigate active network connections and look for unusual or unexpected outbound traffic.

**Validation:** The correct answer is `80`.