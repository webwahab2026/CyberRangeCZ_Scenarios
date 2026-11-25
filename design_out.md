### INFO_LEVEL
The victim machine was attacked by the ransomeware. The attackers encryped some files and left the ransom note behind. Investigate the victim machine to identify the C2 server port number.

### ACCESS_LEVEL
- **Hostname**: victim
- **Username**: cyrano
- **Password**: cyrano
- **Access Method**: SSH

### TRAINING_LEVEL
#### Task 1: C2 Server Communication Port Discovery
The victim machine was attacked by the ransomeware. The attackers encryped some files and left the ransom note behind. Read this note and identify the C2 server port number.

**Step-by-Step Solution:**
1. SSH into the victim machine using the provided credentials.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the home directory of the user.
   ```
   cd /home/cyrano
   ```
3. Read the ransom note file.
   ```
   cat RANSOM_NOTE.txt
   ```
4. Identify the C2 server port number mentioned in the ransom note.

**Hidden Flag:**
The C2 server port number is `4443`.

**Hint 1:**
Use the `cat` command to read the contents of the ransom note file.

**Hint 2:**
Look for the line in the ransom note that mentions connecting to the C2 server.

**Hint 3:**
The port number is specified after the C2 server address in the ransom note.

---

#### Task 2: Identification of the Ransomware Script
The attacker left the ransomware script describing different steps performed by the ransomeware malware. Identify this script.

**Step-by-Step Solution:**
1. SSH into the victim machine using the provided credentials.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the `/tmp` directory.
   ```
   cd /tmp
   ```
3. List all files in the directory, including hidden files.
   ```
   ls -la
   ```
4. Identify the ransomware script file.

**Hidden Flag:**
The ransomware script file is `.crypt_agent`.

**Hint 1:**
Use the `ls -la` command to list all files in the `/tmp` directory.

**Hint 2:**
Look for a file with a name that suggests it is related to encryption or cryptography.

**Hint 3:**
The ransomware script file is a hidden file.

---

#### Task 3: Exfiltration Remote Destination
Analyze the script identified in the previous step to find the remote destination used to send files to the exfiltration server.

**Step-by-Step Solution:**
1. SSH into the victim machine using the provided credentials.
   ```
   ssh cyrano@192.168.90.10
   ```
2. Navigate to the `/tmp` directory.
   ```
   cd /tmp
   ```
3. Read the contents of the ransomware script file.
   ```
   cat .crypt_agent
   ```
4. Identify the remote destination used for exfiltration by checking the `_exfil` function in the script.

**Hidden Flag:**
The remote destination for exfiltration is `exfil-server:/var/exfil/victim/`.

**Hint 1:**
Use the `cat` command to read the contents of the ransomware script file.

**Hint 2:**
Look for the `_exfil` function in the script.

**Hint 3:**
The remote destination is specified as an argument to the `rsync` command in the `_exfil` function.