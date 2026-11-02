Day 6 — Complete documentation
# Day 6: Linux Services and systemd

## 1. Introduction

Today I learned about Linux services and systemd.

A service is a background program that performs a specific task on a Linux system. Examples include networking, SSH, logging and security monitoring.

Services help Linux systems perform important functions without requiring users to start every program manually.

## 2. What is systemd?

systemd is a system and service manager used by many modern Linux distributions.

It is responsible for:
- Starting services during system boot.
- Managing running services.
- Monitoring service states.
- Managing service dependencies.
- Starting and stopping services.

A systemd unit is a resource that systemd manages. Examples include services, mount points and timers.

## 3. The systemctl command

`systemctl` means system control.

It is used to inspect and manage systemd services and units.

### Check the status of a service

```bash
systemctl status NetworkManager


Explanation:
- systemctl - system control utility.
- status - displays the current state of a unit.
- NetworkManager - the networking service being inspected.
List running services
systemctl list-units --type=service


Explanation:
- list-units - lists units currently loaded by systemd.
- --type=service - filters the output to service units.
List installed service unit files
systemctl list-unit-files --type=service


This displays service unit files and their enablement states.
4. Understanding service states
Some important service states include:
State	Meaning
active (running)	The service is currently running.
active (exited)	The service completed its task successfully but has no continuously running process.
inactive (dead)	The service is not currently running.
failed	The service encountered an error.

5. Understanding enablement states
State	Meaning
enabled	Configured to start automatically during the appropriate boot process.
disabled	Not configured to start automatically.
static	Cannot normally be enabled directly; it may be started by another unit.
masked	Prevented from being started through systemd.
alias	An alternative name for another unit.
indirect	Usually enabled through another unit or mechanism.

Important:
A service can be enabled but inactive. Enabled describes its startup configuration, while active describes its current runtime state.
6. Practical Wazuh service monitoring
I used my Ubuntu Wazuh virtual machine to inspect the three main Wazuh services.

The following command was executed on Ubuntu, not Kali:
sudo systemctl status wazuh-manager wazuh-indexer wazuh-dashboard --no-pager


Explanation:
- sudo - runs the command with administrator privileges.
- systemctl - system control utility.
- status - displays service information.
- wazuh-manager - Wazuh analysis and management service.
- wazuh-indexer - stores and indexes security information.
- wazuh-dashboard - provides the web-based interface.
- --no-pager - displays the output directly in the terminal.
All three services were reported as active and running during the check.
7. Checking whether services are active
Commands executed on the Ubuntu Wazuh VM:
systemctl is-active wazuh-manager
systemctl is-active wazuh-indexer
systemctl is-active wazuh-dashboard


The output was:
active
active
active


This confirmed that all three services were running at the time of inspection.
8. Checking whether services are enabled
Commands executed on Ubuntu:
systemctl is-enabled wazuh-manager
systemctl is-enabled wazuh-indexer
systemctl is-enabled wazuh-dashboard


The services were enabled.

This means they were configured to start automatically through their systemd startup configuration.
9. Understanding service dependencies
Services sometimes depend on other services or system components.

To inspect dependencies, I used:
systemctl list-dependencies wazuh-dashboard


I also inspected the manager:
systemctl list-dependencies wazuh-manager


One dependency observed was:

NetworkManager-wait-online.service

This service helps ensure that network connectivity is ready before services that depend on network availability proceed.
10. Why this matters in cybersecurity
Understanding Linux services is important for cybersecurity because:
- Security tools often run as background services.
- SOC analysts need to check whether monitoring services are running.
- Failed services can interrupt security monitoring.
- Attackers may attempt to interfere with security services.
- Service dependencies can help explain startup and operational problems.
In a SOC environment, checking service status is a useful troubleshooting skill.
11. Day 6 knowledge check
1. What is systemd?

Answer: A system and service manager used to manage Linux services and other units.

2. What command checks the status of a service?

Answer: systemctl status service-name

3. What does enabled mean?

Answer: The service is configured to start automatically through the appropriate startup process.

4. Can a service be enabled but inactive?

Answer: Yes. It can be configured for automatic startup but not currently running.

5. Which command displays service dependencies?

Answer: systemctl list-dependencies service-name

6. What does active (running) mean?

Answer: The service is currently running.
12. Day 6 Summary
Today I learned:
- What Linux services are.
- What systemd does.
- How to inspect service status.
- How to list service units.
- The difference between active and enabled.
- How to inspect service dependencies.
- How to monitor Wazuh Manager, Indexer and Dashboard services.
I also learned that service monitoring is an important skill for Linux administration and SOC operations.

Day 6 Status: Completed
