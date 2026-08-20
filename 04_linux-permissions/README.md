# 🔐 Linux File Permissions

Linux file permissions control who can read, write, or execute files and directories.

Understanding permissions is an important part of Linux system administration and cybersecurity.

## 📚 Permission Types

| Permission | Symbol | Value | Meaning |
|---|---|---:|---|
| Read | `r` | 4 | Read file contents |
| Write | `w` | 2 | Modify file contents |
| Execute | `x` | 1 | Execute a file |

Permissions are assigned to three categories:

- **User** — Owner of the file
- **Group** — Users belonging to the file's group
- **Others** — All other users

## 🔍 Reading Permissions

A command such as:

bash
ls -l

can display permissions such as:

-rw-r--r--

The permission section can be understood as:

- rw- r-- r--
  │   │   │
  │   │   └── Others
  │   └────── Group
  └────────── Owner

The first character indicates the file type:

-  → Regular file
d  → Directory
🛠️ chmod

chmod is used to change file permissions.

Add execute permission
chmod u+x permissions.txt

Where:

u = user/owner
+ = add permission
x = execute
Remove execute permission
chmod u-x permissions.txt

This removes execute permission from the owner.

🔢 Numeric Permissions

Linux also represents permissions using numbers:

r = 4
w = 2
x = 1

Examples:

rwx = 7
rw- = 6
r-x = 5
r-- = 4
Example: 755
chmod 755 permissions.txt

Means:

Owner  → 7 → rwx
Group  → 5 → r-x
Others → 5 → r-x

Therefore:

755 = rwxr-xr-x
Example: 644
chmod 644 permissions.txt

Means:

Owner  → 6 → rw-
Group  → 4 → r--
Others → 4 → r--

Therefore:

644 = rw-r--r--
🧪 Hands-on Practice

Commands practiced:

mkdir linux-day4
cd linux-day4
touch permissions.txt
ls -l
chmod u+x permissions.txt
ls -l
chmod u-x permissions.txt
ls -l
chmod 755 permissions.txt
ls -l

The permission changes were observed using ls -l.

🔐 Cybersecurity Relevance

Incorrect file permissions can create security risks by allowing unauthorized users to:

Read sensitive information
Modify important files
Execute unauthorized programs
Access files they should not have access to

Linux permissions are therefore important when securing systems and investigating security incidents.

🎯 What I Learned
The meaning of r, w, and x
User, group, and other permissions
How to inspect permissions with ls -l
How to modify permissions with chmod
Symbolic permission notation
Numeric permission notation
Why file permissions matter in cybersecurity
