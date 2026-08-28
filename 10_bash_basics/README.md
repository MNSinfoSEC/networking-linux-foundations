# 🐧 Bash Basics

Bash scripting allows Linux users to automate repetitive tasks and execute multiple commands using a script.

Bash is an important skill for system administration and cybersecurity automation.

---

## 📚 What I Learned

- Bash scripts
- Shebang
- Variables
- User input
- `echo`
- `read`
- `if` statements
- File permissions
- Making scripts executable

---

## 1️⃣ Creating a Bash Script

A Bash script commonly starts with:

```bash
#!/bin/bash

This is called the shebang and specifies the interpreter used to execute the script.

Example:

#!/bin/bash

echo "Hello, Linux!"
echo "This is my Day 10 Bash practice."
2️⃣ Running a Bash Script

First, make the script executable:

chmod +x hello.sh

Then run it:

./hello.sh
3️⃣ Variables

Variables can store information that can be used later in a script.

Example:

name="Manasa"
course="Cybersecurity"

echo "Name: $name"
echo "Learning: $course"

The $ symbol is used to access the value stored in a variable.

4️⃣ User Input

The read command allows a script to receive input from the user.

Example:

read -p "Enter your name: " name

echo "Hello, $name!"
5️⃣ Conditional Statements

Bash can make decisions using if statements.

Example:

if [ "$number" -gt 10 ]; then
    echo "The number is greater than 10."
else
    echo "The number is 10 or less."
fi

This checks whether a number is greater than 10.

🧰 Commands Practiced
nano
chmod +x
./script.sh
echo
read
if
🔐 Cybersecurity Relevance

Bash scripting is useful in cybersecurity because many security tasks involve Linux systems.

Scripts can be used to automate tasks such as:

Checking system information
Monitoring processes
Checking network configuration
Searching logs
Checking disk usage
Performing repetitive security checks

Instead of manually running many commands, a Bash script can perform them automatically.

Example workflow:

Bash Script
     ↓
Collect Information
     ↓
Check System
     ↓
Check Network
     ↓
Check Logs
     ↓
Display Results
🎯 What I Learned
How to create Bash scripts
What the shebang means
How to create variables
How to accept user input
How to use echo and read
How to use if statements
How to make scripts executable
How Bash can be used for cybersecurity automation
