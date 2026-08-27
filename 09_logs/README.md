# 📋 Linux Logs

Linux logs contain records of events and activities that happen on a system.

Logs are useful for troubleshooting, system administration, monitoring, and cybersecurity investigations.

---

## 🧠 What Are Logs?

A Linux system records different types of events, such as:

- System events
- Login attempts
- Service activity
- Authentication events
- Kernel messages
- Application activity

These records can help understand what happened on a system.

---

## 📂 Log Directory

Most Linux system logs are stored under:

```bash
/var/log

To view the contents:

ls /var/log

Different Linux distributions may contain different log files.

🔎 Viewing Log Files

The cat command can display the contents of a file:

cat /var/log/syslog

If the output is too large, use:

less /var/log/syslog

Press:

q

to exit less.

🔐 Authentication Logs

Authentication-related logs can contain information about login and authentication events.

On Ubuntu, authentication information is commonly stored in:

/var/log/auth.log

To view it:

sudo less /var/log/auth.log

These logs can be useful when investigating login activity.

🔍 Searching Logs

The grep command can search for specific text.

Example:

grep "failed" /var/log/auth.log

This searches for lines containing the word failed.

Another example:

grep "sudo" /var/log/auth.log

This searches for entries related to sudo.

🕐 Viewing Recent Logs

The tail command displays the end of a file.

tail /var/log/syslog

To continuously watch new entries:

sudo tail -f /var/log/syslog

Press:

Ctrl + C

to stop.

📊 System Logs with journalctl

Modern Linux systems using systemd can use:

journalctl

To view recent entries:

journalctl

To view the latest entries:

journalctl -n 20

To follow new log entries:

journalctl -f

Press:

Ctrl + C

to stop.

🧰 Commands Practiced
ls /var/log
cat /var/log/syslog
less /var/log/syslog
sudo less /var/log/auth.log
grep "failed" /var/log/auth.log
grep "sudo" /var/log/auth.log
tail /var/log/syslog
sudo tail -f /var/log/syslog
journalctl
journalctl -n 20
journalctl -f
🔐 Cybersecurity Relevance

Logs are extremely important in cybersecurity.

Security analysts can use logs to investigate:

Failed login attempts
Successful logins
sudo activity
Service activity
System events
Suspicious behaviour

A basic investigation might look like:

Suspicious Activity
        ↓
Check Relevant Logs
        ↓
Search for Important Events
        ↓
Identify Time & User
        ↓
Investigate Further

Logs can provide valuable evidence about what happened on a Linux system.

🎯 What I Learned
What Linux logs are
Where Linux logs are stored
How to view log files
How to search logs using grep
How to view recent entries using tail
How to monitor logs in real time
How to use journalctl
Why logs are important for cybersecurity investigations
