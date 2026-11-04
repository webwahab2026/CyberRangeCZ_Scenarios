### INFO_LEVEL
The victim machine was attacked by the Linux P2P Ransom botnet malware. The attackers encrypted some files and left a ransom note behind. Your task is to investigate the attack, identify the indicators of compromise, and take appropriate actions to mitigate the threat.

### ACCESS_LEVEL
You have SSH access to the victim machine with the following credentials:
- Username: cyrano
- Password: cyrano

### TRAINING_LEVEL 1
**Task description:**
The attackers encrypted some files and left a ransom note behind. Read this note and identify the C2 server port number.

**Step-by-step solution to find the hidden flag:**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the home directory of the user cyrano.
3. Read the contents of the file `RANSOM_NOTE.txt`.
4. Identify the C2 server port number mentioned in the ransom note.

**Three hints with used commands:**
1. Use the `ssh` command to connect to the victim machine.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the home directory using the `cd` command.
   ```
   cd /home/cyrano
   ```
3. Read the contents of the ransom note using the `cat` command.
   ```
   cat RANSOM_NOTE.txt
   ```

**Hidden flag:** `4443`

### TRAINING_LEVEL 2
**Task description:**
The attacker left the ransomware script describing different steps performed by the ransomware malware. Identify this script.

**Step-by-step solution to find the hidden flag:**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the `/tmp` directory.
3. Look for hidden files using the `ls -la` command.
4. Identify the ransomware script.

**Three hints with used commands:**
1. Use the `ssh` command to connect to the victim machine.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the `/tmp` directory using the `cd` command.
   ```
   cd /tmp
   ```
3. Look for hidden files using the `ls -la` command.
   ```
   ls -la
   ```

**Hidden flag:** `.crypt_agent`

### TRAINING_LEVEL 3
**Task description:**
Analyze the script identified in the previous step to find the remote destination used to send files to the exfiltration server.

**Step-by-step solution to find the hidden flag:**
1. SSH into the victim machine using the provided credentials.
2. Navigate to the `/tmp` directory.
3. Read the contents of the ransomware script using the `cat` command.
4. Identify the remote destination used for exfiltration.

**Three hints with used commands:**
1. Use the `ssh` command to connect to the victim machine.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the `/tmp` directory using the `cd` command.
   ```
   cd /tmp
   ```
3. Read the contents of the ransomware script using the `cat` command.
   ```
   cat .crypt_agent
   ```

**Hidden flag:** `exfil-server:/var/exfil/victim/`