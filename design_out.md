# Supreme Backdoor Factory Incident Response Scenario

## INFO_LEVEL
The organization has detected unusual network activity originating from the target host. Initial analysis suggests a potential compromise involving a backdoor. Your task is to investigate and respond to this incident.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Investigate the unusual network activity on the target host.

**Description:**
While monitoring network traffic, you noticed unusual outbound connections from the target host. Your task is to identify the source of this activity.

**Hint:**
Check the systemd services and look for any unusual or unauthorized services.

**Validation:**
The hidden flag is the name of the suspicious service.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service maintains persistence.

**Description:**
You have identified a suspicious service running on the target host. Your next step is to understand how this service maintains persistence across reboots.

**Hint:**
Investigate the systemd timers and services to find the persistence mechanism.

**Validation:**
The hidden flag is the name of the systemd timer responsible for the service's persistence.

## TRAINING_LEVEL 3
**Task:** Identify the file associated with the suspicious activity.

**Description:**
Now that you have identified the suspicious service and its persistence mechanism, locate the executable or file associated with this activity.

**Hint:**
Check the service unit file for the ExecStart path.

**Validation:**
The hidden flag is the path to the suspicious file.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. Each task is feasible within the given topology and Ansible configuration, and all indicators are derived from the MISP event or the sandbox details.