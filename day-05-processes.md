# Day 5: Understanding Linux Processes

## 1. Introduction

A process is a program that is currently running in a Linux system.

Linux uses processes to manage applications, background services, and system activities.

## 2. Viewing Processes

### The ps command

```bash
ps


Displays processes associated with the current terminal session.
The ps aux command
ps aux


Displays processes running across the system.

Important columns:
- USER: Account running the process.
- PID: Process ID.
- %CPU: CPU usage.
- %MEM: Memory usage.
- STAT: Process status.
- COMMAND: Program being executed.
3. Viewing Processes by User
ps -u michael


Displays processes belonging to the user michael.
4. Monitoring Processes
top


Displays a live, continuously updating view of system processes and resource usage.
5. Searching for Processes
pgrep -a systemd


Searches for processes matching systemd and displays their command lines.
pgrep -a gnome-shell


Searches for processes matching gnome-shell.
6. Inspecting a Specific Process
ps -p 3598 -f


Displays detailed information about process ID 3598.

Important fields:
- PID: Process ID.
- PPID: Parent Process ID.
- UID: User running the process.
- CMD: Command associated with the process.
7. Understanding Parent and Child Processes
Linux processes can create other processes.
- PID identifies a process.
- PPID identifies its parent process.
The parent-child relationship helps administrators understand how processes are connected.
8. Linux Process Signals
A signal is a notification sent to a process.

To list available signals:
kill -l


Important signals:
Signal	Number	Meaning
SIGHUP	1	Hangup
SIGINT	2	Interrupt
SIGKILL	9	Force termination
SIGTERM	15	Graceful termination request
SIGSTOP	19	Suspend a process
SIGCONT	18	Resume a suspended process

SIGTERM allows a process to handle a termination request.

SIGKILL forces a process to stop and cannot be handled or ignored.
9. Key Lessons
- Processes are running programs.
- Every process has a PID.
- PPID identifies the parent process.
- ps displays process information.
- top monitors processes in real time.
- pgrep searches for processes.
- Linux signals communicate with processes.
10. Conclusion
Understanding Linux processes is important for system administration, troubleshooting, and cybersecurity monitoring.

These skills help security analysts understand running applications and investigate system activity.

### Step 4: Save the file

1. Press `Ctrl + O` to save.
2. Press `Enter` to confirm the filename.
3. Press `Ctrl + X` to exit Nano.

Once you've exited Nano, tell me. We'll check the file before committing it to GitHub.
