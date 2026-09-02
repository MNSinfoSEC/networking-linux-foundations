# 🐧 Bash Scripting

## Overview

Bash scripting allows us to combine Linux commands and programming logic into a single script.

Instead of manually performing the same commands repeatedly, we can create a Bash script to automate the task.

Bash scripting is especially useful in:

- Linux administration
- System automation
- File management
- Log analysis
- System monitoring
- Backup tasks
- Cybersecurity
- Incident response

---

## 🎯 Learning Objectives

- Understand Bash scripts
- Understand variables
- Use command substitution
- Work with user input
- Use conditional statements
- Understand exit status
- Use comparison operators
- Work with loops
- Use command-line arguments
- Automate basic Linux tasks
- Understand how Bash can be useful in cybersecurity

---

# 1. What is Bash?

**Bash** stands for **Bourne Again SHell**.

It is a command-line shell commonly used on Linux systems.

Bash allows users to:

- Execute commands
- Manage files
- Work with processes
- Configure systems
- Automate tasks
- Create scripts

Example:

```bash
ls
pwd
whoami

These commands can also be placed inside a script.

2. What is Bash Scripting?

A Bash script is a text file containing a sequence of commands that Bash can execute.

Example:

#!/bin/bash

echo "Hello, World!"

Save the file as:

hello.sh

Make it executable:

chmod +x hello.sh

Run it:

./hello.sh

Output:

Hello, World!
3. Shebang

A Bash script usually begins with:

#!/bin/bash

This is called the shebang.

It tells the operating system which interpreter should be used to execute the script.

For Bash:

#!/bin/bash
4. Comments

Comments are used to explain code.

Bash comments begin with #.

Example:

#!/bin/bash

# Display the current username
whoami

Comments are ignored when the script runs.

They make scripts easier to understand and maintain.

5. Variables

Variables are used to store information.

Example:

name="Manasa"

To access the variable:

echo "$name"

Output:

Manasa
Important

There should be no spaces around =.

Correct:

name="Manasa"

Incorrect:

name = "Manasa"
6. User Input

The read command is used to receive input from the user.

Example:

#!/bin/bash

echo "Enter your name:"
read name

echo "Hello, $name"

A user can enter:

Manasa

The script then prints:

Hello, Manasa
7. Command Substitution

Command substitution allows the output of a command to be stored in a variable.

Syntax:

variable=$(command)

Example:

username=$(whoami)

echo "Current user: $username"

Another example:

current_directory=$(pwd)

echo "Current directory: $current_directory"

This is useful when scripts need information from Linux commands.

8. Conditional Statements

Bash supports conditional logic using if.

Example:

#!/bin/bash

age=20

if [ "$age" -ge 18 ]; then
    echo "Adult"
fi
9. if-else

Example:

#!/bin/bash

age=16

if [ "$age" -ge 18 ]; then
    echo "Adult"
else
    echo "Minor"
fi
10. if-elif-else

Multiple conditions can be checked using elif.

#!/bin/bash

marks=75

if [ "$marks" -ge 90 ]; then
    echo "Grade A"
elif [ "$marks" -ge 60 ]; then
    echo "Grade B"
else
    echo "Grade C"
fi
11. Comparison Operators

Bash uses different operators for numerical comparisons.

Operator	Meaning
-eq	Equal
-ne	Not equal
-gt	Greater than
-lt	Less than
-ge	Greater than or equal
-le	Less than or equal

Example:

if [ "$age" -ge 18 ]; then
    echo "Eligible"
fi
12. String Comparisons

Strings can also be compared.

name="admin"

if [ "$name" = "admin" ]; then
    echo "Administrator"
fi

Common operators include:

=       Equal
!=      Not equal
-z      Empty string
-n      Non-empty string

Example:

if [ -z "$name" ]; then
    echo "Name is empty"
fi
13. File Tests

Bash can check properties of files and directories.

Common operators:

Operator	Meaning
-f	Regular file exists
-d	Directory exists
-r	File is readable
-w	File is writable
-x	File is executable
-e	File or directory exists

Example:

if [ -f "test.txt" ]; then
    echo "File exists"
else
    echo "File does not exist"
fi

This is particularly useful for automation scripts.

14. Exit Status

Linux commands return an exit status after execution.

Generally:

0 = Success
Non-zero = Error or failure

The special variable:

$?

contains the exit status of the previous command.

Example:

ls /home
echo $?

If the command succeeds, the output will normally be:

0

Example with a nonexistent directory:

ls /does-not-exist
echo $?

A non-zero value indicates that the command failed.

15. Using Exit Status in Scripts

Exit status can be used to determine whether an operation succeeded.

Example:

#!/bin/bash

mkdir test_folder

if [ "$?" -eq 0 ]; then
    echo "Directory created successfully"
else
    echo "Failed to create directory"
fi

A more practical approach is to place the command directly inside the condition:

if mkdir test_folder; then
    echo "Directory created successfully"
else
    echo "Failed to create directory"
fi
16. Loops

Loops allow commands to be repeated.

Bash commonly provides:

for
while
until
for Loop

Example:

for number in 1 2 3 4 5
do
    echo "$number"
done

Output:

1
2
3
4
5
while Loop

A while loop continues while a condition is true.

count=1

while [ "$count" -le 5 ]
do
    echo "$count"
    count=$((count + 1))
done
17. Command-Line Arguments

Bash scripts can accept arguments when they are executed.

Example script:

#!/bin/bash

echo "Hello, $1"

Run:

./hello.sh Manasa

Output:

Hello, Manasa

Here:

$1 = First argument

Other useful variables include:

$0 = Script name
$1 = First argument
$2 = Second argument
$# = Number of arguments
$@ = All arguments
18. Useful Bash Variables
Variable	Meaning
$0	Script name
$1	First argument
$2	Second argument
$#	Number of arguments
$@	All arguments
$?	Previous command's exit status
$HOME	User's home directory
$USER	Current username
$PWD	Current working directory

Example:

echo "User: $USER"
echo "Home: $HOME"
echo "Directory: $PWD"
19. Simple System Information Script

Bash can combine multiple Linux commands.

#!/bin/bash

echo "===== System Information ====="

echo "Username: $(whoami)"
echo "Hostname: $(hostname)"
echo "Current Directory: $(pwd)"
echo "Date: $(date)"

This demonstrates:

Variables
Command substitution
Linux commands
Output
Script structure
20. File Checking Script

A simple script can check whether a file exists.

#!/bin/bash

read -p "Enter filename: " file

if [ -f "$file" ]; then
    echo "File exists."
else
    echo "File does not exist."
fi

This can be useful when automating file-related tasks.

21. Basic Backup Script

Bash can also automate simple backup operations.

Example:

#!/bin/bash

source="important.txt"
backup="important.txt.backup"

if [ -f "$source" ]; then
    cp "$source" "$backup"
    echo "Backup created successfully."
else
    echo "Source file not found."
fi

This demonstrates how Bash can automate administrative tasks.

22. Bash and Cybersecurity

Bash is highly useful in cybersecurity because many security tools and servers run on Linux.

Security professionals can use Bash to automate:

Log analysis
File searches
System checks
Permission checks
Process monitoring
Network information gathering
Incident response tasks
Security auditing

Example:

#!/bin/bash

echo "Current user:"
whoami

echo "Open network connections:"
ss -tuln

echo "Running processes:"
ps aux

This combines several Linux commands into one simple security-oriented script.

23. Bash for Log Analysis

Logs contain valuable information for security monitoring.

For example:

grep "Failed password" /var/log/auth.log

This searches for failed SSH authentication attempts on systems where that log path is used.

A script can later be created to automate this type of analysis.

Example:

#!/bin/bash

echo "Failed authentication attempts:"
grep "Failed password" /var/log/auth.log

The exact log location can vary between Linux distributions and configurations.

24. Why Bash Matters for Cybersecurity

A cybersecurity professional may need to perform repetitive tasks quickly.

Instead of manually entering:

command
command
command
command

a script can automate them:

Bash Script
     ↓
Multiple Commands
     ↓
Automated Task
     ↓
Result

This saves time and reduces repetitive manual work.

🧪 Practice Tasks

Try creating the following scripts yourself.

1. System Information

Display:

Username
Hostname
Current directory
Current date
2. File Checker

Ask the user for a filename and determine whether it exists.

3. Directory Checker

Ask for a directory and determine whether it exists.

4. Number Checker

Ask for a number and determine whether it is:

Positive
Negative
Zero
5. Simple Loop

Print numbers from 1 to 10.

6. Argument Script

Create a script that accepts a name as an argument:

./greet.sh Manasa

and prints:

Hello, Manasa
🔐 Cybersecurity Connection

Bash scripting connects Linux knowledge with cybersecurity automation.

The progression is:

Linux Commands
       ↓
Bash Scripting
       ↓
Automation
       ↓
Log Analysis
       ↓
System Monitoring
       ↓
Security Automation

Bash will be especially useful when working with:

Linux servers
SOC environments
Logs
Incident response
Security monitoring
System administration
🧠 Key Takeaways
Bash is a command-line shell commonly used on Linux
Bash scripts automate multiple commands
#!/bin/bash specifies the Bash interpreter
Variables store values
read accepts user input
$(command) performs command substitution
if, elif, and else provide decision-making
Bash supports numerical and string comparisons
File tests can check files and directories
Exit status indicates whether a command succeeded
Loops allow repetitive tasks
Command-line arguments make scripts reusable
Bash can automate cybersecurity and system administration tasks
🛠️ Commands & Concepts Practiced
echo
read
chmod
if
elif
else
for
while
grep
cp
mkdir
whoami
hostname
pwd
date
ps
ss
