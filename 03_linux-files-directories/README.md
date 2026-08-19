# 🐧 Linux Files & Directories

This section covers basic Linux commands used to create, view, copy, move, rename, and remove files and directories.

## 📚 Commands Practiced

| Command | Purpose |
|---|---|
| mkdir | Creates a directory |
| touch | Creates an empty file |
| ls | Lists files and directories |
| cp | Copies files or directories |
| mv | Moves or renames files |
| cat | Displays file contents |
| echo | Displays or writes text |
| rm | Removes files |
| cd | Changes directory |
| pwd | Shows the current directory |

## 📁 Creating Directories

The mkdir command creates a new directory.

bash
mkdir linux-day3

📄 Creating Files

The touch command creates an empty file.

touch file1.txt
touch file2.txt
📋 Copying Files

The cp command copies a file.

cp file1.txt documents/

This creates a copy of file1.txt inside the documents directory.

🚚 Moving and Renaming Files

The mv command can move a file:

mv file3.txt documents/

It can also rename a file:

mv file2.txt notes.txt
📖 Reading File Contents

The cat command displays the contents of a file.

cat notes.txt
✏️ Writing to a File

The echo command can be used with > to write text into a file.

echo "Linux Day 3 practice" > notes.txt
🗑️ Removing Files

The rm command removes a file.

rm temporary.txt

⚠️ rm should be used carefully because deleted files are not normally moved to a recycle bin.

🧪 Hands-on Practice

During this exercise, I practiced:

mkdir linux-day3
cd linux-day3
touch file1.txt
touch file2.txt
mkdir documents
cp file1.txt documents/
touch file3.txt
mv file3.txt documents/
mv file2.txt notes.txt
echo "Linux Day 3 practice" > notes.txt
cat notes.txt
rm temporary.txt
🔐 Cybersecurity Relevance

Basic file and directory management is essential when working with Linux systems in cybersecurity.

-These skills are used when:

-Navigating security tools
-Examining files
-Reading logs
-Organizing investigation data
-Working with configuration files
-Managing scripts and security-related files

🎯 What I Learned
-How to create files and directories
-How to navigate directories
-How to copy files
-How to move and rename files
-How to read file contents
-How to write text to files
-How to safely remove files
