# TeamTNT Hildegard Incident Response Scenario

## INFO_LEVEL
The target Kubernetes cluster has been compromised by the TeamTNT Hildegard malware. This backdoor targets Kubernetes clusters, exploiting misconfigured kubelets for initial access. It spreads across containers, establishes C2 connections via tmate reverse shell and IRC channels, and performs cryptojacking operations using xmrig. The malware also searches for cloud credentials and exfiltrates them to C2 servers.

Your task is to investigate and respond to this incident, following the Incident Response profile responsibilities.

## ACCESS_LEVEL
You have SSH access to the target host with the following credentials:
- Host: target (192.168.50.5)
- Username: cyrano
- Password: cyrano

From this host, you can SSH to the next-target host (192.168.50.6) using the same credentials.

## TRAINING_LEVEL 1
**Task:** Investigate the target host for suspicious services or processes that might indicate malware activity.

**Question:** What is the name of the suspicious service running on the target host that appears to be related to the Hildegard malware?

**Hint:** Check running services and look for any that seem unusual or unrelated to normal Kubernetes operations.

## TRAINING_LEVEL 2
**Task:** Determine how the suspicious service is maintaining persistence on the target host.

**Question:** What is the persistence mechanism used by the suspicious service?

**Hint:** Examine systemd services and timers to identify how the service is automatically started.

## TRAINING_LEVEL 3
**Task:** Investigate the lateral movement capabilities of the malware between the target and next-target hosts.

**Question:** What is the name of the service or process responsible for transferring files between the target and next-target hosts?

**Hint:** Look for services or processes that are transferring files or establishing connections between the two hosts.

---

This scenario is designed to align with the provided MISP event, security profile, and sandbox environment. All tasks are based on the actual hosts, services, and configurations present in the sandbox. The scenario focuses on investigating and responding to the TeamTNT Hildegard malware, with tasks that require students to discover information through investigation rather than being explicitly told what to look for.