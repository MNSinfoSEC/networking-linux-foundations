# 🐧 Linux Filesystem

This section covers the basic Linux filesystem structure and commands used to navigate through directories.

## 📂 Linux Filesystem Structure

Linux uses a hierarchical filesystem that begins at the root directory `/`.

text
/
├── home/
├── etc/
├── var/
├── tmp/
├── usr/
├── bin/
└── dev/

📌 Important Directories
Directory	Purpose
/	Root of the filesystem
/home	User home directories
/etc	System configuration files
/var	Variable data and logs
/tmp	Temporary files
/usr	User programs and utilities
/dev	Device files
🛠️ Commands Practiced
pwd

Prints the current working directory.

pwd
ls

Lists files and directories.

ls
ls -l

Displays a detailed listing including permissions, ownership, size, and modification information.

ls -l
cd

Changes the current directory.

cd /
cd ~

Returns to the current user's home directory.

cd ~
🧪 Hands-on Practice

Commands practiced:

pwd
ls
cd /
ls
cd ~
pwd
🔐 Cybersecurity Relevance

Understanding the Linux filesystem is important for cybersecurity because security professionals frequently work with:

User files
Configuration files
System directories
Application data
System logs
Security-related files

In particular:

/home    → User data
/etc     → Configuration
/var/log → System and application logs

These locations become important when investigating systems and security incidents.

🎯 What I Learned
Linux uses a hierarchical filesystem
/ is the root directory
/home contains user directories
/etc contains configuration files
/var contains variable data and logs
pwd shows the current directory
ls lists directory contents
cd changes directories
~ represents the current user's home directory
