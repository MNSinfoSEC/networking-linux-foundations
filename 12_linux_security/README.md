# 🐧 Linux Security Fundamentals

> **Understanding the basic security practices that help protect a Linux system.**

Linux security is not one single feature. It is a combination of:

- 👤 User management
- 🔐 File permissions
- 🛡️ Privilege control
- 🔑 Authentication
- 🌐 Network security
- 📜 Logging and monitoring
- 📦 Software updates
- ⚙️ Secure configuration

The goal is to reduce unnecessary access, detect suspicious activity, and protect system resources.

---

## 🧠 Why Linux Security Matters

Linux is widely used in:

- Servers
- Cloud infrastructure
- Web applications
- Networking devices
- Security tools
- Containers
- Development environments

A poorly configured Linux system can expose sensitive files, services, accounts, or network ports.

A secure system follows the principle:

> **Give users and processes only the access they actually need.**

This is known as the **principle of least privilege**.

---

# 🔐 1. File Permissions

Linux uses permissions to control access to files and directories.

Three basic permission types are:

```text
r → Read
w → Write
x → Execute
```

Three ownership categories are:

```text
u → User / Owner
g → Group
o → Others
```

Example:

```bash
ls -l
```

Output may look like:

```text
-rwxr-xr--
```

This can be understood as:

```text
Owner   → rwx
Group   → r-x
Others  → r--
```

---

# 👤 2. Users and Groups

Linux separates users and groups to control access.

View the current user:

```bash
whoami
```

View groups:

```bash
groups
```

View user information:

```bash
id
```

Example:

```text
uid=1000(user)
gid=1000(user)
groups=1000(user),27(sudo)
```

Groups can provide additional permissions without changing ownership of individual files.

---

# 👑 3. Root User

Linux has a special administrative account called:

```text
root
```

Root has extremely powerful privileges.

It can:

- Modify system files
- Change permissions
- Install software
- Manage users
- Configure services
- Access protected resources

Because root has extensive privileges, using it unnecessarily increases risk.

---

# 🛡️ 4. sudo

Instead of logging in as root for normal work, Linux commonly provides `sudo`.

Example:

```bash
sudo apt update
```

`sudo` allows an authorized user to execute a command with elevated privileges.

The idea is:

```text
Normal User
     ↓
Needs administrative action
     ↓
sudo
     ↓
Elevated privilege
     ↓
Command executes
```

Use elevated privileges only when necessary.

---

# 🔑 5. Authentication

Authentication answers:

> **"Who are you?"**

Linux can authenticate users using mechanisms such as:

- Passwords
- SSH keys
- Pluggable Authentication Modules (PAM)
- Other authentication systems

Check the current user:

```bash
whoami
```

View currently logged-in users:

```bash
who
```

Another useful command:

```bash
w
```

---

# 🔒 6. Strong Authentication

Good authentication practices include:

- Use strong passwords
- Avoid password reuse
- Protect SSH access
- Disable unnecessary accounts
- Use SSH keys where appropriate
- Restrict administrative access

Authentication is only one part of security.

After authentication, the system must also determine what the user is allowed to do.

---

# 🔐 7. Authentication vs Authorization

### Authentication

Determines **who you are**.

```text
"Are you really this user?"
```

### Authorization

Determines **what you are allowed to access**.

```text
"What can this user do?"
```

Simple example:

```text
Login
 ↓
Authentication
 ↓
User identified
 ↓
Authorization
 ↓
Permissions checked
 ↓
Access granted/denied
```

---

# 🧱 8. Firewall

A firewall controls network traffic according to configured rules.

It can help restrict unwanted connections.

Conceptually:

```text
Internet
   │
   ▼
Firewall
   │
   ├── Allowed traffic → ✅
   │
   └── Blocked traffic → ❌
```

On Linux, common firewall tools include:

- `ufw`
- `firewalld`
- `nftables`

---

## 🔍 Checking UFW

On systems using UFW:

```bash
sudo ufw status
```

A firewall should be configured according to the system's actual requirements rather than simply blocking everything.

---

# 🌐 9. Open Ports and Services

Every unnecessary network service can increase the attack surface.

Check listening sockets with:

```bash
ss -tuln
```

You may see information such as:

```text
Local Address
Port
Protocol
State
```

For example:

```text
0.0.0.0:22
```

could indicate an SSH service listening on port 22.

---

# 🎯 Attack Surface

The **attack surface** is the collection of points where an attacker could potentially interact with a system.

Examples:

```text
Open ports
Running services
User accounts
Applications
Web servers
Remote access
Exposed files
```

A useful security principle is:

> **Reduce what does not need to be exposed.**

---

# 📦 10. Software Updates

Keeping software updated is an important security practice.

Updates can include:

- Bug fixes
- Security patches
- Stability improvements
- New features

On Debian/Ubuntu-based systems:

```bash
sudo apt update
```

Then:

```bash
sudo apt upgrade
```

The exact package-management commands depend on the Linux distribution.

---

# 🧹 11. Remove Unnecessary Services

If a service is not required, consider disabling or removing it.

First identify running services:

```bash
systemctl --type=service
```

Check a specific service:

```bash
systemctl status ssh
```

Do not disable services blindly.

First understand what the service does and whether the system depends on it.

---

# 📜 12. Logs and Security

Logs are extremely important for security monitoring.

Linux systems can record events such as:

- Authentication attempts
- Service activity
- System events
- Errors
- Privilege usage

Depending on the distribution and configuration, logs may be available through:

```bash
journalctl
```

For example:

```bash
journalctl -p warning
```

This can help identify warning-level events.

---

# 🚨 Failed Login Attempts

Authentication logs can provide useful security information.

On systems where authentication logs are stored in `/var/log/auth.log`:

```bash
grep "Failed password" /var/log/auth.log
```

The exact log location varies between distributions and configurations.

This can help identify repeated failed authentication attempts.

---

# 🔍 13. Monitoring Login Activity

Useful commands include:

```bash
who
```

```bash
w
```

```bash
last
```

These can provide information about current or previous login activity, depending on system configuration.

---

# 🕵️ 14. Suspicious Processes

Processes can be inspected using:

```bash
ps aux
```

or:

```bash
top
```

Another useful command is:

```bash
htop
```

if it is installed.

When investigating suspicious activity, useful questions include:

```text
What process is running?
Who owns it?
What command started it?
What resources is it using?
Is it expected?
```

---

# 🔎 15. File Ownership

Check file ownership with:

```bash
ls -l
```

Example:

```text
-rw-r--r-- 1 user user file.txt
```

Here:

```text
Owner → user
Group → user
```

Unexpected ownership can sometimes indicate a configuration problem or security issue.

---

# ⚠️ 16. Dangerous Permissions

Some permission configurations can create unnecessary risk.

For example, giving everyone write access to a sensitive file:

```text
-rw-rw-rw-
```

means the owner, group, and others have write permission.

Sensitive system files should not generally be writable by everyone.

Always understand what a permission change does before applying it.

---

# 🧮 Permission Numbers

Linux permissions can also be represented numerically.

```text
r = 4
w = 2
x = 1
```

Therefore:

```text
rwx = 7
rw- = 6
r-x = 5
r-- = 4
```

Example:

```bash
chmod 755 script.sh
```

means:

```text
Owner  → rwx → 7
Group  → r-x → 5
Others → r-x → 5
```

---

# 🔑 17. SSH Security

SSH provides remote access to Linux systems.

SSH commonly uses:

```text
TCP Port 22
```

Basic SSH usage:

```bash
ssh username@host
```

Security considerations include:

- Use strong authentication
- Prefer SSH keys where appropriate
- Restrict unnecessary access
- Keep SSH software updated
- Monitor authentication logs
- Avoid exposing SSH unnecessarily

---

# 🧩 18. Principle of Least Privilege

One of the most important security concepts is:

> **Users and processes should have only the permissions they need.**

Example:

```text
❌ Everyone → Full Access

        vs.

✅ User → Required Access
   Group → Required Access
   Admin → Administrative Access
```

Least privilege reduces the potential impact of compromised accounts or applications.

---

# 🛡️ 19. Defense in Depth

Linux security should not depend on a single protection mechanism.

Instead, multiple layers can work together:

```text
          🔐 Authentication
                  ↓
          👤 User Controls
                  ↓
          📁 Permissions
                  ↓
          🧱 Firewall
                  ↓
          📦 Updates
                  ↓
          📜 Logging
                  ↓
          🔍 Monitoring
```

If one layer fails, other layers can still provide protection.

This approach is called **defense in depth**.

---

# 🧪 Practical Security Checklist

Use the following commands on your own Linux system or lab VM.

### 1. Identify the current user

```bash
whoami
```

### 2. Check user identity and groups

```bash
id
```

### 3. Inspect file permissions

```bash
ls -la
```

### 4. Check listening ports

```bash
ss -tuln
```

### 5. Check running services

```bash
systemctl --type=service
```

### 6. Check firewall status

```bash
sudo ufw status
```

### 7. Inspect recent logins

```bash
last
```

### 8. Inspect system logs

```bash
journalctl
```

---

# 🧪 Mini Investigation

Try answering these questions on your Linux machine:

```text
1. Who am I logged in as?
2. What groups am I a member of?
3. Which ports are listening?
4. Which services are running?
5. Is a firewall enabled?
6. What recent logins exist?
7. Are there failed authentication attempts?
8. Which files have unusual permissions?
```

The goal is not just to run commands.

The goal is to understand **what the output means**.

---

# 🔐 Linux Security Mindset

When looking at a Linux system, start asking:

```text
WHO?
 ↓
Who has access?

WHAT?
 ↓
What services are running?

WHERE?
 ↓
Where are sensitive files?

HOW?
 ↓
How can users access the system?

WHY?
 ↓
Why does this service/permission exist?

CAN IT BE REDUCED?
 ↓
Can unnecessary access be removed?
```

This mindset is more valuable than memorizing commands.

---

# 🧠 Key Concepts

```text
Linux Security
│
├── 👤 Users
├── 👥 Groups
├── 🔐 Permissions
├── 👑 Root
├── 🛡️ sudo
├── 🔑 Authentication
├── ✅ Authorization
├── 🧱 Firewall
├── 🌐 Network Services
├── 📦 Updates
├── 📜 Logs
├── 🔍 Monitoring
├── 🔑 SSH
├── 🎯 Attack Surface
├── 🛡️ Least Privilege
└── 🧩 Defense in Depth
```

---

# 📝 Quick Revision

### What is the principle of least privilege?

Giving users and processes only the permissions they actually need.

### What is `sudo`?

A mechanism that allows authorized users to execute commands with elevated privileges.

### What is the root user?

A highly privileged administrative account.

### What does a firewall do?

Controls network traffic according to configured rules.

### How can you see listening ports?

```bash
ss -tuln
```

### How can you inspect file permissions?

```bash
ls -l
```

### How can you inspect processes?

```bash
ps aux
```

### How can you inspect system logs?

```bash
journalctl
```

### Why are software updates important?

They can include security fixes and patches for known vulnerabilities.

---

# ✅ What I Learned

- [x] Linux security fundamentals
- [x] Users and groups
- [x] File permissions
- [x] Root privileges
- [x] `sudo`
- [x] Authentication
- [x] Authorization
- [x] Firewall basics
- [x] Open ports and services
- [x] Attack surface
- [x] Software updates
- [x] Linux logs
- [x] Login monitoring
- [x] Process inspection
- [x] SSH security basics
- [x] Principle of least privilege
- [x] Defense in depth
