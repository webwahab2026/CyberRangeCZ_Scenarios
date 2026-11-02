# Rhombus Botnet Investigation

## INFO_LEVEL
The Rhombus botnet is a Linux DDoS botnet targeting VPS and IoT devices. It has persistence and dropper capabilities but does not perform lateral movement or data exfiltration. This scenario focuses on investigating and containing a Rhombus botnet infection on compromised systems.

## ACCESS_LEVEL
You have SSH access to the bot1 host with the following credentials:
- Username: cyrano
- Password: cyrano

## TRAINING_LEVEL 1
**Task:** Identify and investigate an unauthorized or suspicious service responsible for periodic external communication.

**Solution:**
1. Log in to bot1 using the provided credentials: `ssh cyrano@bot1`
2. List all running services: `systemctl list-units --type=service --all`
3. Look for suspicious services, particularly those with unusual names or descriptions
4. Investigate the suspicious service by checking its status: `systemctl status <service_name>`
5. Examine the service's configuration file, typically located in `/etc/systemd/system/`
6. The hidden flag is the name of the suspicious service

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services
2. Look for services with unusual names or descriptions
3. Check the service status with `systemctl status <service_name>`
4. The hidden flag is the name of the suspicious service

## TRAINING_LEVEL 2
**Task:** Identify the service responsible for generating abnormal volumes of network traffic.

**Solution:**
1. On bot1, list all running services: `systemctl list-units --type=service --all`
2. Look for another suspicious service, different from the one identified in TRAINING_LEVEL 1
3. Investigate the suspicious service by checking its status: `systemctl status <service_name>`
4. Examine the service's configuration file, typically located in `/etc/systemd/system/`
5. The hidden flag is the name of the suspicious service responsible for network flooding

**Hints:**
1. Use `systemctl list-units --type=service --all` to list all services
2. Look for services with unusual names or descriptions related to network activity
3. Check the service status with `systemctl status <service_name>`
4. The hidden flag is the name of the suspicious service

## TRAINING_LEVEL 3
**Task:** Determine how the suspicious service identified in TRAINING_LEVEL 1 is automatically started after reboot.

**Solution:**
1. On bot1, investigate the persistence mechanism of the suspicious service identified in TRAINING_LEVEL 1
2. Check for systemd timers associated with the service: `systemctl list-timers --all`
3. Look for timers with names related to the suspicious service
4. Examine the timer configuration file, typically located in `/etc/systemd/system/`
5. The hidden flag is the name of the timer unit file (without the .timer extension)

**Hints:**
1. Use `systemctl list-timers --all` to list all systemd timers
2. Look for timers with names related to the suspicious service
3. Check the timer configuration file in `/etc/systemd/system/`
4. The hidden flag is the name of the timer unit file (without the .timer extension)