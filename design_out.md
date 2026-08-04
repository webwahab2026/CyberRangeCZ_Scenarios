# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a sophisticated Linux rootkit designed to hide its presence and manipulate system processes. It targets both Intel and ARM processors and is capable of intercepting and modifying system calls. This rootkit has been detected in your network environment, and your task is to investigate and respond to this security incident.

## ACCESS_LEVEL
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is part of a network that includes an attacker host and another victim host. You can use standard Linux commands and forensic tools to investigate the compromise.

## TRAINING_LEVEL 1
**Task:** Identify evidence that a shared library has been injected into system processes.

**Description:** The Umbreon rootkit is known to inject a shared library into system processes to manipulate their behavior. Your task is to investigate the loaded libraries in system processes and identify any evidence of unauthorized code injection.

**Hint:** Use tools like `ldd`, `lsof`, or `strace` to examine the libraries loaded by system processes. Look for any libraries that appear suspicious or out of place.

**Validation:** The hidden flag for this task is the identifier of the shared library used by the rootkit.

## TRAINING_LEVEL 2
**Task:** Determine whether a system-wide preload configuration has been modified to execute unauthorized code.

**Description:** The Umbreon rootkit may modify the system-wide preload configuration to ensure that its shared library is loaded by all processes. Your task is to investigate the preload configuration and determine if it has been tampered with.

**Hint:** Examine the contents of `/etc/ld.so.preload` and look for any paths that appear suspicious or out of place.

**Validation:** The hidden flag for this task is the identifier of the preload configuration used by the rootkit.

## TRAINING_LEVEL 3
**Task:** Locate files or directories concealed from normal system utilities.

**Description:** The Umbreon rootkit may create hidden files or directories to store its components or configuration data. Your task is to investigate the filesystem and identify any concealed artifacts.

**Hint:** Use tools like `find`, `ls`, or `stat` to examine the filesystem. Look for any files or directories that are hidden or have unusual permissions.

**Validation:** The hidden flag for this task is the identifier of the hidden artifact used by the rootkit.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to encourage investigation and discovery of the rootkit's components and behaviors without revealing the hidden implementation details. The validation flags are used exclusively for automated assessment.