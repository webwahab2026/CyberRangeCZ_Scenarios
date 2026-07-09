### Scenario: BiBi-Linux Wiper Incident Response

**INFO_LEVEL:**
The BiBi-Linux wiper malware has been detected in your network. This malware is designed to corrupt files with random data, manipulate partition tables, and append mocking 'BiBi' extensions. It does not have command-and-control (C2) capabilities or lateral movement features but does exfiltrate data. The malware targets Linux systems.

**ACCESS_LEVEL:**
You have access to the workstation (192.168.50.5) as user 'cyrano' with password 'cyrano'. From this host, you can SSH to the file-server (192.168.50.6) using the same credentials.

---

**TRAINING_LEVEL 1:**

**Task:** Identify and investigate suspicious file destruction activity.

**Description:**
Examine the system logs and file artifacts on the workstation to identify any suspicious file destruction activity. Look for evidence of files being overwritten with random data or renamed with random hex strings.

**Hint:**
Check the system logs in /var/log/ for any unusual activity. Also, examine the contents of the /data/company_files directory for any signs of file corruption or unusual filenames.

**Flag:** Destructive Activity Identifier

---

**TRAINING_LEVEL 2:**

**Task:** Investigate malware execution logs and forensic artifacts.

**Description:**
Analyze the logs and artifacts left by the BiBi-Linux wiper malware on the workstation. Look for any logs or files that indicate the malware's execution and the extent of the damage caused.

**Hint:**
Check the /var/log/disk-maintenance.log file for detailed logs of the malware's activity. Also, examine the /var/cache/.trigger_received file for any indicators of the malware's trigger mechanism.

**Flag:** Log Artifact Identifier

---

**TRAINING_LEVEL 3:**

**Task:** Trace malware spread from one host to another.

**Description:**
Investigate how the BiBi-Linux wiper malware spread from the workstation to the file-server. Look for any scripts, services, or logs that indicate lateral movement activity.

**Hint:**
Examine the /usr/local/bin/net-sync.sh script on the workstation for any signs of lateral movement. Also, check the /home/cyrano/net-sync.log file for logs of the spreader's activity.

---

**Q/A:**

**Question 1:**
What is the primary behavior of the BiBi-Linux wiper malware?

**Answer 1:**
The BiBi-Linux wiper malware is designed to corrupt files with random data, manipulate partition tables, and append mocking 'BiBi' extensions referencing Israeli Prime Minister Netanyahu.

**Question 2:**
What are the key indicators of the BiBi-Linux wiper malware's activity?

**Answer 2:**
Key indicators include files being overwritten with random data, files being renamed with random hex strings, and logs being cleared to hinder forensics. Additionally, the malware creates a systemd service and timer for persistence, and it reports completion to a C2 server.

**Question 3:**
How did the BiBi-Linux wiper malware spread from the workstation to the file-server?

**Answer 3:**
The malware spread through a script called net-sync.sh, which copied the wiper binary to the file-server and executed it using SSH. The spreader script is set to run on boot via a systemd timer.