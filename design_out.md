### INFO_LEVEL
The victim machine was attacked by the Linux P2P Ransom botnet malware. The attackers encrypted some files and left a ransom note behind. Your task is to investigate the attack, identify the indicators of compromise, and take appropriate actions to mitigate the threat.

### ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Username: cyrano
- Password: cyrano

### TRAINING_LEVEL 1
**Task description**
The attackers encrypted some files and left a ransom note behind. Read this note and identify the C2 server port number.

**Step-by step solution to find the hidden flag**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the home directory of the user cyrano.
3. Read the contents of the file `RANSOM_NOTE.txt`.
4. Identify the C2 server port number mentioned in the ransom note.

**Three hints with used commands**
1. Use the `cd` command to navigate to the home directory.
2. Use the `cat` command to read the contents of the file.
3. Look for the line that mentions the C2 server port number.

### TRAINING_LEVEL 2
**Task description**
The attacker left the ransomware script describing different steps performed by the ransomeware malware. Identify this script.

**Step-by step solution to find the hidden flag**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the `/tmp` directory.
3. Look for hidden files using the `ls -la` command.
4. Identify the ransomware script.

**Three hints with used commands**
1. Use the `cd /tmp/` command to navigate to the `/tmp` directory.
2. Use the `ls -la` command to list all files, including hidden ones.
3. Look for a file that resembles a script.

### TRAINING_LEVEL 3
**Task description**
Analyze the script identified in the previous step to find the remote destination used to send files to the exfiltration server.

**Step-by step solution to find the hidden flag**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the `/tmp` directory.
3. Read the contents of the ransomware script identified in the previous step.
4. Identify the remote destination used for exfiltration.

**Three hints with used commands**
1. Use the `cd /tmp/` command to navigate to the `/tmp` directory.
2. Use the `cat` command to read the contents of the script.
3. Look for the `rsync` command and its arguments in the `_exfil()` function.