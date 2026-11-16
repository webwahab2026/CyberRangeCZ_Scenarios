```json
{
  "INFO_LEVEL": {
    "title": "Sofacy Malware Investigation",
    "description": "Investigate a compromised Linux host infected with the Sofacy malware family, specifically the Fysbis backdoor. Identify and analyze suspicious activities, including C2 communication, data collection, and lateral movement.",
    "difficulty": "Intermediate",
    "approach": "Defence-oriented",
    "scenario_type": "Exercise",
    "learning_objectives": [
      "Enumerate running and inactive services to identify suspicious activities.",
      "Correlate network listeners, service configurations, and running processes to identify communication ports.",
      "Investigate systemd service activation and scheduling to identify persistence mechanisms.",
      "Detect unauthorized remote file transfers and identify the source and destination of suspicious activity.",
      "Apply targeted firewall controls to contain threats without disrupting legitimate services."
    ]
  },
  "ACCESS_LEVEL": {
    "entry_host": "target",
    "access_method": "SSH",
    "username": "cyrano",
    "password": "cyrano",
    "instructions": "Use SSH to connect to the target host with the provided credentials."
  },
  "TRAINING_LEVELS": [
    {
      "level": 1,
      "title": "Suspicious C2 Service Discovery",
      "task_description": "Security monitoring has detected an unusual network-facing component on the compromised host. Investigate the running services and identify the service responsible for the suspicious activity.",
      "learning_objective": "Enumerate running and inactive services, distinguish legitimate from suspicious services, look for unfamiliar service names or misspellings of legitimate services. Services with unusual descriptions or startup behavior.",
      "nice_alignment": {
        "tasks": ["SP 0233", "SP 0234"],
        "knowledge": ["KN 0001", "KN 0002"],
        "skills": ["SK 0001", "SK 0002"]
      },
      "target_host": "target",
      "evidence": [
        "Unusual network-facing component detected."
      ],
      "solution": [
        {
          "step": 1,
          "action": "List all services, including inactive ones.",
          "command": "systemctl list-units --type=service --all",
          "expected_result": "List of all services, including inactive ones."
        },
        {
          "step": 2,
          "action": "List all service unit files.",
          "command": "systemctl list-unit-files --type=service",
          "expected_result": "List of all service unit files."
        },
        {
          "step": 3,
          "action": "Identify the suspicious service.",
          "command": "systemctl list-units --type=service --state=running",
          "expected_result": "List of running services, including the suspicious one."
        }
      ],
      "hints": [
        "Look for services with unusual names or descriptions.",
        "Check the list of running services for any unfamiliar entries.",
        "Use the command 'systemctl list-units --type=service --state=running' to identify the suspicious service."
      ],
      "validation": {
        "type": "flag",
        "source": "service name",
        "method": "Identify the suspicious service name."
      },
      "qa": {
        "question": "What is the name of the suspicious service?",
        "answer": "systemkernelservicedefender.service"
      }
    },
    {
      "level": 2,
      "title": "C2 Communication Discovery (Port)",
      "task_description": "An unfamiliar network service appears to be involved in unauthorized communication with an external system. Investigate the service and determine the network port associated with this communication.",
      "learning_objective": "Correlate network listeners, service configurations, and running processes to identify the communication port. Inspect the C2 service definition and pay particular attention to ExecStart, which specifies the command launched by the service with a port number as argument.",
      "nice_alignment": {
        "tasks": ["SP 0233", "SP 0234"],
        "knowledge": ["KN 0001", "KN 0002"],
        "skills": ["SK 0001", "SK 0002"]
      },
      "target_host": "target",
      "evidence": [
        "Unfamiliar network service involved in unauthorized communication."
      ],
      "solution": [
        {
          "step": 1,
          "action": "Inspect the suspicious service configuration.",
          "command": "systemctl cat systemkernelservicedefender.service",
          "expected_result": "Service configuration details, including the port number."
        },
        {
          "step": 2,
          "action": "Check the status of the suspicious service.",
          "command": "systemctl status systemkernelservicedefender.service",
          "expected_result": "Status information for the suspicious service."
        },
        {
          "step": 3,
          "action": "List all network listeners.",
          "command": "ss -tulnp",
          "expected_result": "List of network listeners, including the suspicious port."
        }
      ],
      "hints": [
        "Inspect the service configuration for the port number.",
        "Check the status of the suspicious service for additional details.",
        "Use the command 'ss -tulnp' to list all network listeners."
      ],
      "validation": {
        "type": "flag",
        "source": "C2 port number",
        "method": "Identify the network port associated with the suspicious communication."
      },
      "qa": {
        "question": "What is the network port associated with the suspicious communication?",
        "answer": "80"
      }
    },
    {
      "level": 3,
      "title": "Suspicious Data Collection Service Discovery",
      "task_description": "System information appears to be collected automatically without an authorized administrative purpose. Investigate the host and identify the service responsible for this activity.",
      "learning_objective": "Discover suspicious systemd services, including periodically executed services, and distinguish legitimate administrative activity from unauthorized data collection.",
      "nice_alignment": {
        "tasks": ["SP 0233", "SP 0234"],
        "knowledge": ["KN 0001", "KN 0002"],
        "skills": ["SK 0001", "SK 0002"]
      },
      "target_host": "target",
      "evidence": [
        "System information collected automatically without an authorized administrative purpose."
      ],
      "solution": [
        {
          "step": 1,
          "action": "List all services, including inactive ones.",
          "command": "systemctl list-units --type=service --all",
          "expected_result": "List of all services, including inactive ones."
        },
        {
          "step": 2,
          "action": "List all service unit files.",
          "command": "systemctl list-unit-files --type=service",
          "expected_result": "List of all service unit files."
        },
        {
          "step": 3,
          "action": "List all timers.",
          "command": "systemctl list-timers --all",
          "expected_result": "List of all timers, including the suspicious one."
        },
        {
          "step": 4,
          "action": "Inspect the suspicious timer configuration.",
          "command": "systemctl cat local-inventory.timer",
          "expected_result": "Timer configuration details."
        }
      ],
      "hints": [
        "Look for services with unusual names or descriptions.",
        "Check the list of timers for any unfamiliar entries.",
        "Use the command 'systemctl list-timers --all' to identify the suspicious timer."
      ],
      "validation": {
        "type": "flag",
        "source": "service name",
        "method": "Identify the service responsible for the suspicious data collection activity."
      },
      "qa": {
        "question": "What is the name of the service responsible for the suspicious data collection activity?",
        "answer": "local-inventory.service"
      }
    }
  ]
}
```