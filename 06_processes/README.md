# ⚙️ Linux Processes

A process is a running instance of a program or command in a Linux system.

Linux assigns each process a unique **Process ID (PID)**.

Understanding processes is important for system administration and cybersecurity.

---

## 🔄 What is a Process?

When a program or command runs, Linux creates a process for it.

Example:

text
Command
   ↓
Program starts
   ↓
Linux creates a process
   ↓
Process receives a PID
🆔 Process ID (PID)

Every running process has a unique Process ID.

To see the PID of the current shell:

echo $$

The number returned is the PID of the current shell.

👀 Viewing Processes
ps

Displays processes associated with the current terminal:

ps
ps aux

Displays detailed information about running processes:

ps aux

Important information includes:

User
PID
CPU usage
Memory usage
Command
📊 Monitoring Processes

The top command displays processes in real time.

top

It allows users to monitor:

CPU usage
Memory usage
Running processes
Process IDs

Press:

q

to exit top.

🔍 Finding Processes

The grep command can be used to filter process information.

Example:

ps aux | grep bash

The | symbol is called a pipe.

It sends the output of one command to another command.

⏳ Background Processes

A command can be executed in the background using &.

Example:

sleep 30 &

Linux starts the command as a background process.

The system returns a PID that can be used to identify the process.

🛑 Terminating a Process

A process can be terminated using the kill command.

kill PID

Example:

kill 12345

The PID should be replaced with the actual process ID.

Only terminate processes that you understand or have permission to manage.

🧪 Commands Practiced
ps
ps aux
echo $$
top
ps aux | grep bash
sleep 30 &
kill PID
🔐 Cybersecurity Relevance

Process monitoring is important in cybersecurity.

Security professionals can investigate:

Suspicious processes
Unexpected programs
High CPU or memory usage
Processes running under unusual users
Potential malicious activity

A basic process investigation can follow:

Suspicious activity
       ↓
Find running process
       ↓
Identify PID
       ↓
Identify user
       ↓
Investigate the process
       ↓
Take appropriate action
🎯 What I Learned
What a Linux process is
What a PID is
How to view running processes
How to monitor processes
How to run commands in the background
How to terminate a process
Why process monitoring is important for cybersecurity
