# Lesson 5: Linux Processes

## Objective

Understand Linux processes, Process IDs (PIDs), process monitoring, background processes, and terminating processes.

---

## 1. What Is a Process?

A process is a currently running instance of a program or application.

Every running process is assigned a unique Process ID (PID).

---

## 2. Process ID (PID)

PID stands for **Process ID**.

Linux assigns a unique number to each running process so that the system can identify and manage it.

Example:

```bash
ps
```

Example output:

```text
PID TTY          TIME CMD
4011 pts/0    00:00:00 zsh
8323 pts/0    00:00:00 ps
```

---

## 3. Viewing Processes with `ps`

The `ps` command displays a snapshot of processes associated with the current terminal.

```bash
ps
```

It is useful for quickly checking processes currently running in the terminal.

---

## 4. Viewing Processes with `ps aux`

The `ps aux` command provides a detailed list of processes from all users.

```bash
ps aux
```

Important columns include:

* USER — User who owns the process
* PID — Process ID
* %CPU — CPU usage
* %MEM — Memory usage
* STAT — Process state
* COMMAND — Command that started the process

---

## 5. Process States

The `STAT` column shows the state of a process.

Common states include:

* `R` — Running
* `S` — Sleeping
* `D` — Uninterruptible sleep
* `T` — Stopped
* `Z` — Zombie
* `I` — Idle kernel thread

---

## 6. Monitoring Processes with `top`

The `top` command provides a live, continuously updating view of running processes.

```bash
top
```

Unlike `ps`, which provides a snapshot, `top` continuously updates the process information.

Press `q` to exit `top`.

---

## 7. Monitoring Processes with `htop`

`htop` provides an interactive process-monitoring interface.

```bash
htop
```

It makes it easier to view CPU, memory, and process information.

Press `q` to exit.

---

## 8. Running Processes in the Background

The `&` symbol can be used to run a command in the background.

Example:

```bash
sleep 500 &
```

This runs the `sleep` program as a background process.

The process can then be identified using:

```bash
ps aux | grep sleep
```

---

## 9. Terminating a Process

The `kill` command can be used to terminate a process using its PID.

Example:

```bash
kill 2468
```

The number `2468` represents the PID of the process.

### Practical Exercise

A test process was created:

```bash
sleep 500 &
```

The process was identified with:

```bash
ps aux | grep sleep
```

The PID was then used to terminate the process:

```bash
kill PID
```

The process was checked again to confirm that it was no longer running.

---

## 10. Cybersecurity Relevance

Process monitoring is useful in cybersecurity because unusual or unexpected processes can indicate system problems or potentially suspicious activity.

For example, if a server suddenly becomes very slow, commands such as:

```bash
ps aux
```

```bash
top
```

and:

```bash
htop
```

can be used to investigate CPU usage, memory usage, and running processes.

Process investigation can therefore help identify abnormal system behavior.

---

## 11. APT Troubleshooting During the Lesson

While installing `htop`, the package manager initially returned:

```text
Unable to locate package htop
```

The Kali APT repository configuration was checked and found to contain an incorrect repository address.

The repository entry was corrected to:

```text
deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware
```

After updating the package lists, `htop` was successfully installed.

---

## Commands Practiced

```bash
ps
ps aux
top
htop
sleep 500 &
ps aux | grep sleep
kill PID
```

---

## Key Takeaways

* A process is a running instance of a program.
* PID means Process ID.
* `ps` provides a process snapshot.
* `ps aux` provides detailed information about processes from all users.
* `top` provides a live process view.
* `htop` provides an interactive process-monitoring interface.
* `&` runs a command in the background.
* `kill PID` can terminate a process.
* Process monitoring is useful for troubleshooting and cybersecurity investigations.
