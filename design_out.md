# Umbreon Rootkit Investigation

## INFO_LEVEL
The Umbreon rootkit is a Linux rootkit that targets both x86 and ARM systems. It is designed to hide its presence and provide backdoor access to the attacker. The rootkit includes components for hiding processes, files, and network connections. In this scenario, you will investigate a compromised system to identify and analyze the Umbreon rootkit.

## ACCESS_LEVEL
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is connected to the network `192.168.50.0/24`. You can also access the victim2 host using SSH with the same credentials.

## TRAINING_LEVEL 1
### Task: Identify evidence that a shared library has been injected into system processes.
The system appears to be behaving unusually, and you suspect that a shared library has been injected into system processes. Your task is to investigate and identify evidence of this injection.

#### Step-by-Step Solution:
1. SSH into the victim host using the provided credentials.
2. Check the loaded shared libraries for system processes using the `ldd` command.
3. Look for any suspicious or unauthorized libraries in the output.
4. Investigate the suspicious library further to confirm its malicious nature.

#### Hints:
1. Use the `ps` command to list all running processes.
2. Use the `ldd` command followed by the process name to check loaded libraries.
3. Look for libraries that are not part of the standard system libraries.
4. The hidden flag is the name of the suspicious library.

## TRAINING_LEVEL 2
### Task: Determine whether a system-wide preload configuration has been modified to execute unauthorized code.
You suspect that the system-wide preload configuration might have been tampered with to execute unauthorized code. Your task is to investigate and determine if this is the case.

#### Step-by-Step Solution:
1. SSH into the victim host using the provided credentials.
2. Check the contents of the `/etc/ld.so.preload` file.
3. Look for any suspicious or unauthorized libraries listed in the file.
4. Investigate the suspicious library further to confirm its malicious nature.

#### Hints:
1. Use the `cat` command to view the contents of the `/etc/ld.so.preload` file.
2. Look for any libraries that are not part of the standard system libraries.
3. The hidden flag is the name of the suspicious library listed in the preload file.

## TRAINING_LEVEL 3
### Task: Locate files or directories concealed from normal system utilities.
You suspect that there might be files or directories on the system that are concealed from normal system utilities. Your task is to investigate and locate these hidden artifacts.

#### Step-by-Step Solution:
1. SSH into the victim host using the provided credentials.
2. Use alternative forensic techniques to search for hidden files or directories.
3. Investigate any suspicious files or directories found.
4. Confirm the malicious nature of the hidden artifacts.

#### Hints:
1. Use the `find` command with appropriate options to search for hidden files or directories.
2. Look for files or directories with unusual names or permissions.
3. The hidden flag is the name of the hidden artifact.