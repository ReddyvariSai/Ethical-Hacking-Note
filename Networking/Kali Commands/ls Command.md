# 🐧 Linux ls Command – Complete Guide

The ls command is one of the most commonly used Linux commands. It lists files and directories and provides various options to view detailed information.

## 📌 Syntax ls [options]


By default, ls displays files and directories in the current folder. Options allow you to modify how the output appears.

# 📋 Common ls Command Options
Option	Description
| Option | Description                                        |
| ------ | -------------------------------------------------- |
| `-l`   | Long format (shows permissions, owner, size, date) |
| `-a`   | Show hidden files                                  |
| `-h`   | Human-readable file sizes                          |
| `-R`   | Recursive listing                                  |
| `-t`   | Sort by modification time                          |
| `-r`   | Reverse sorting order                              |
| `-1`   | Display one file per line                          |
| `-d`   | List directories, not their contents               |
| `-F`   | Show file type indicators                          |
| `-L`   | Follow symbolic links                              |
| `-X`   | Sort files by extension                            |

----
# 📂 Basic Usage
List Files and Directories
```
ls
```
<img width="768" height="75" alt="image" src="https://github.com/user-attachments/assets/7df8f5c6-8d10-457f-aac9-4697d55c5082" />

Displays all files and folders in the current directory.

## 📁 Identify File Types
```
ls -F
```
<img width="768" height="95" alt="image" src="https://github.com/user-attachments/assets/5b40a2e3-23d5-4cc1-bf31-86477d118db1" />

### Output Symbols:
/ → Directory, * → Executable, @ → Symbolic link, = → Socket.
## 🧾 Separate Files with Commas
To print directories and files separated by a comma, run the following:
```
ls -m
```
<img width="768" height="73" alt="image" src="https://github.com/user-attachments/assets/69e5b329-28c7-46ee-8f4a-5ca3ed42636b" />

🔤 Add Quotation Marks
Run ls with the -Q option to add quotation marks to all directories and files:
```
ls -Q
```
<img width="768" height="88" alt="image" src="https://github.com/user-attachments/assets/42539012-adff-4979-b0a2-3067c2fe5b99" />


🔢 Display Inode Numbers
To get the Inode (index node) number of all directories and files, type:
```
ls -i
```
<img width="768" height="107" alt="image" src="https://github.com/user-attachments/assets/c41a2b60-779c-42b7-bd96-9150e3ad5d8c" />

🔄 Reverse Order Sorting
To sort directories and files in the reverse order, type the following:
```
ls -r
```
<img width="768" height="72" alt="image" src="https://github.com/user-attachments/assets/fee543e8-ca43-42b5-98ad-396172007b98" />

🕒 Sort by Modification Time
Use the following to sort directories and files by modification time, with the most recently modified items displayed first:
```
ls -t
```
<img width="768" height="69" alt="image" src="https://github.com/user-attachments/assets/e7aee1d5-031b-4c88-8647-a762db2c0ad1" />


🧩 Sort by File Extension
To sort directories and files alphabetically by the entry extension type, run:
```
ls -X
```
<img width="768" height="71" alt="image" src="https://github.com/user-attachments/assets/31927675-5ab4-4445-8fec-3f3f2951a1dc" />


----
#🤖 Note: If you want to learn how to sort file contents, refer to the Linux sort command.
----

👀 View Hidden Files

```
ls -a
```

Hidden files start with a dot (.).

🌳 View Directory Tree
```
ls -R
```

With detailed info:
```
ls -lR
```

📃 Long Listing Format
```
ls -l
```

## Shows:
Permissions
Owner
Group
Size
Date & Time
Filename
## 📑 List All Files (Including Hidden)
```
ls -la
```

📄 List Specific File Types
```
ls *.txt
```
🆔 Show UID and GID
```
ls -n
```
📊 Human-Readable File Sizes
```
ls -lh
```
⏱️ Sort by Date (Reverse Order)
```
ls -ltr
```

📦 Sort Files by Size
```
ls -lS
```
📁 View Files in a Specific Directory
```
ls -l /tmp
```

🙈 Hide File Owner
```
ls -g
```
📘 View All ls Options
```
ls --help
```
ℹ️ Check ls Version
```
ls --version
```
# ✅ Conclusion

The ls command is essential for navigating and managing files in Linux. With its many options, you can:

View file details

Sort files efficiently

Display hidden files

Analyze directory structures
----
📘 Next Step: Learn how to create files in Linux using commands like touch, nano, and cat.

