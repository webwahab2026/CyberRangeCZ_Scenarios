### INFO_LEVEL
**Scenario Title:** Kobalos Malware Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a potential Kobalos malware infection on a high-performance computing (HPC) cluster. Kobalos is a complex, multiplatform malware that targets HPC clusters and other high-profile systems. It grants remote access to the file system, provides the ability to spawn terminal sessions, and allows proxying connections to other Kobalos-infected servers. It also includes a credential stealer component that captures SSH credentials.

**Learning Objectives:**
- Identify and investigate suspicious services running on a host.
- Determine how the suspicious service is automatically started after reboot.
- Locate the executable or file associated with the suspicious activity.

### ACCESS_LEVEL
**Entry Host:** target
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

### TRAINING_LEVEL 1
**Task:** Suspicious Service Discovery
**Description:**
While monitoring the target host, you notice unusual network activity. Investigate the running services on the target host to identify any unauthorized or suspicious services.
**Hint:** Use standard system commands to list running services and check their legitimacy.
**Validation:**
- The student must identify the suspicious service running on the target host.
- The hidden flag is the service name.

### TRAINING_LEVEL 2
**Task:** Persistence Discovery
**Description:**
Now that you have identified the suspicious service, determine how it is automatically started after reboot. This will help you understand the persistence mechanism used by the malware.
**Hint:** Check systemd services, cron jobs, and other common persistence mechanisms.
**Validation:**
- The student must identify the persistence mechanism used by the suspicious service.
- The hidden flag is the service name or persistence identifier.

### TRAINING_LEVEL 3
**Task:** Suspicious File Discovery
**Description:**
Locate the executable or file associated with the suspicious service. This will help you gather more information about the malware and its behavior.
**Hint:** Correlate processes with files on disk and identify malicious artifacts.
**Validation:**
- The student must locate the executable or file associated with the suspicious service.
- The hidden flag is the filename or file path.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide students through the investigation of a Kobalos malware infection, focusing on service discovery, persistence mechanisms, and file discovery. The scenario ensures that all tasks are feasible within the given sandbox environment.