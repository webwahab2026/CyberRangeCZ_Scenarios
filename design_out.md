# Kinsing Rootkit Investigation

## INFO_LEVEL
The Kinsing rootkit has been detected in your organization's Linux environment. This rootkit is known to exploit CVE-2023-46604 in Apache ActiveMQ to infect systems with cryptominers and establish persistence. Your task is to investigate and contain this threat.

## ACCESS_LEVEL
You have SSH access to the victim host with the following credentials:
- Hostname: victim (192.168.50.5)
- Username: cyrano
- Password: cyrano

You also have SSH access to the attacker host with the same credentials:
- Hostname: attacker (192.168.40.5)

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.

**Objective:** Investigate loaded libraries and detect unauthorized code injection.

**Hint:** Check the loaded libraries for all running processes and look for any unusual or unexpected libraries.

**Validation:** The hidden flag is the name of the shared library used for injection.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.

**Objective:** Identify preload-based persistence and code injection mechanisms.

**Hint:** Examine the system-wide library preload configuration file.

**Validation:** The hidden flag is the path to the preload configuration file.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.

**Objective:** Apply forensic techniques to identify hidden filesystem artifacts.

**Hint:** Use alternative methods to list files and directories, as standard utilities may be compromised.

**Validation:** The hidden flag is the path to a concealed directory or file.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks focus on investigating the Kinsing rootkit's behavior, including shared library injection, system-wide preload modification, and hidden artifacts. The scenario adheres to the sandbox constraints and uses only the indicators and services available in the sandbox environment.