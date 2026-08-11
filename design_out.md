---
scenario:
  name: Fysbis Linux Backdoor Incident Response
  description: |
    A suspicious activity has been detected within your organization's Linux environment. As a member of the incident response team, your task is to investigate, analyze, and respond to the incident using the available infrastructure. The environment consists of several Ubuntu Linux hosts, including a suspected compromised machine. Your investigation should focus on identifying unauthorized services, persistence mechanisms, and malicious artifacts, all while following best practices for incident response.

  INFO_LEVEL:
    overview: |
      You are part of the incident response team investigating suspicious activity on a Linux host. The organization has observed unusual network connections and possible persistence mechanisms. Your goal is to identify the root cause, determine how the threat maintains access, and locate any malicious files or artifacts. Use your skills in service enumeration, process analysis, and file system investigation to uncover the details.

    objectives:
      - Enumerate running services and identify any unauthorized or suspicious activity.
      - Investigate how the suspicious activity persists after reboot.
      - Locate and analyze any files or executables associated with the suspicious activity.

    environment:
      hosts:
        - target (Ubuntu, user: cyrano/cyrano)
        - next-target (Ubuntu, user: cyrano/cyrano)
        - c2-server (Ubuntu, user: cyrano/cyrano)
      network:
        - The "target" host is the primary point of investigation.
        - SSH access is available to "target" as user "cyrano" with sudo privileges.

    rules_of_engagement:
      - Do not modify or remove system files unless instructed.
      - Document your findings for each step.
      - Focus your investigation on the "target" host unless otherwise specified.

  ACCESS_LEVEL:
    entry_host: target
    entry_method: SSH
    username: cyrano
    password: cyrano
    privilege: sudo
    notes: |
      Begin your investigation by connecting to the "target" host via SSH using the provided credentials. You have full sudo privileges to perform your analysis.

  TRAINING_LEVEL:
    - id: 1
      title: Suspicious Service Discovery
      description: |
        The security operations center has reported unusual network activity originating from the "target" host. Your first task is to enumerate all running services and identify any that appear unauthorized or suspicious. Focus on services that are not part of a standard Ubuntu installation or that you do not recognize as part of normal operations.

        **Task:**  
        - List all active systemd services and running processes.
        - Identify the name of the suspicious service responsible for the unusual activity.

        **Validation:**  
        - Submit the exact name of the suspicious service as your answer.

      question: What is the name of the suspicious service running on the "target" host?
      hint: |
        Use `systemctl list-units --type=service` and `ps aux` to enumerate services and processes. Look for services that do not match standard system services or that have unusual names.

      flag_type: service_name

    - id: 2
      title: Persistence Mechanism Discovery
      description: |
        After identifying the suspicious service, your next step is to determine how it achieves persistence on the "target" host. Investigate the system to find out how this service is configured to start automatically after a reboot.

        **Task:**  
        - Investigate the persistence mechanism used by the suspicious service.
        - Identify the specific system component (e.g., systemd unit, cron job) responsible for persistence.

        **Validation:**  
        - Submit the name of the persistence mechanism (e.g., the systemd unit name) as your answer.

      question: What is the name of the persistence mechanism used by the suspicious service on the "target" host?
      hint: |
        Check `/etc/systemd/system/` and use `systemctl status <service>` to find out how the service is started. Look for custom or non-standard unit files.

      flag_type: persistence_identifier

    - id: 3
      title: Suspicious File Discovery
      description: |
        To complete your investigation, locate the file or executable associated with the suspicious service you have identified. This file is likely responsible for the malicious activity observed on the host.

        **Task:**  
        - Correlate the suspicious service or process with its executable file on disk.
        - Identify the full path to the suspicious file.

        **Validation:**  
        - Submit the full file path of the suspicious executable as your answer.

      question: What is the full path to the suspicious file associated with the unauthorized service on the "target" host?
      hint: |
        Use `systemctl status <service>` and `ps aux` to find the process and its executable path. You can also check the `ExecStart` line in the relevant systemd unit file.

      flag_type: file_path

---