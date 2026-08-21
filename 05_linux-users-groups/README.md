# 👥 Linux Users & Groups

Linux uses users and groups to control access to files, directories, and system resources.

Understanding users and groups is an important part of Linux administration and cybersecurity.

## 👤 Users

A user account represents an individual account on a Linux system.

Each user has a unique **User ID (UID)**.

The current user can be identified using:

bash
whoami

Example:

manasa
🆔 User and Group Information

The id command displays information about the current user.

id

It can show:

UID
GID
Primary group
Additional groups

To check another user:

id username

The root account can be checked with:

id root

The root user normally has:

UID = 0
👥 Groups

Groups allow multiple users to be managed together.

A user can belong to one or more groups.

To view the groups associated with the current user:

groups

Groups are useful for controlling access to shared resources.

👀 Logged-in Users

The who command displays users currently logged into the system.

who
🔐 Root User

The root user is the Linux superuser.

Root has extensive privileges over the system and can perform administrative operations that normal users cannot.

The root account is associated with:

UID 0
🛡️ sudo

sudo allows an authorized user to execute a command with elevated privileges.

Example:

sudo apt update

Because elevated privileges can make significant system changes, sudo should be used carefully.

🔗 Users, Groups & Permissions

Users and groups are directly connected to Linux file permissions.

For example:

-rwxr-xr--

Permissions are divided into:

User → Group → Others

This allows Linux to control who can:

Read a file
Modify a file
Execute a file
🧪 Hands-on Practice

Commands practiced:
-whoami
-id
-groups
-who
-id root

These commands were used to identify the current user, UID, groups, logged-in users, and root account information.

🔐 Cybersecurity Relevance

Understanding users and groups is important for:
-Access control
-Privilege management
-System administration
-Security investigations
-Identifying unauthorized accounts
-Understanding file permissions
-Detecting privilege-related issues

A cybersecurity professional should understand who has access to what and why.

🎯 What I Learned
-What Linux users are
-What UIDs and GIDs represent
-How groups work
-How to identify the current user
-How to view group membership
-What the root user is
-How sudo provides elevated privileges
-How users and groups relate to file permissions
