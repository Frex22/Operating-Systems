# Phase 1: Unix/Linux Basics

Let's start building your foundation in Unix/Linux operating systems. Understanding these core concepts will be essential before diving into more advanced OS programming.

## 1. Introduction to Unix/Linux Architecture

### Core Philosophy
- **Everything is a file**: Devices, processes, and system information are represented as files
- **Small, composable tools**: Programs that do one thing well and can be combined
- **Plain text configuration**: System settings stored in readable text files
- **Multiuser design**: Built from the ground up for multiple concurrent users

### System Architecture Layers
- **Hardware**: Physical components (CPU, memory, disks)
- **Kernel**: Core of OS that interfaces directly with hardware
- **Shell**: Command interpreter that interfaces with the kernel
- **Utilities**: Standard programs and tools
- **Applications**: User programs built on top of the system

## 2. Shell Fundamentals

### Common Shells
- **Bash** (Bourne Again Shell): Most common default shell
- **Zsh**: Extended Bash with additional features
- **Fish**: User-friendly shell with advanced features
- **Ksh** (Korn Shell): Combines features of other shells

### Basic Shell Navigation
```bash
pwd                 # Print working directory
ls                  # List files and directories
ls -la              # List all files with details
cd /path/to/dir     # Change directory
cd ..               # Move up one directory
cd ~                # Go to home directory
```

### File Operations
```bash
touch file.txt      # Create empty file
mkdir dir_name      # Create directory
cp source dest      # Copy files
mv source dest      # Move/rename files
rm file.txt         # Remove file
rm -r dir_name      # Remove directory recursively
```

## 3. File System Architecture

### Hierarchical Structure
- **/** (root): Top-level directory
- **/bin**: Essential command binaries
- **/etc**: System configuration files
- **/home**: User home directories
- **/lib**: Shared libraries
- **/proc**: Virtual filesystem for process info
- **/var**: Variable data (logs, spool files)
- **/dev**: Device files
- **/usr**: User programs, libraries, documentation

### File Types
- Regular files
- Directories
- Symbolic links
- Block special files (block devices)
- Character special files (character devices)
- Named pipes (FIFOs)
- Sockets

### Inodes and File System Structure
- **Inodes**: Data structures storing file metadata
- **Superblocks**: File system metadata
- **Data blocks**: Actual file contents

## 4. Permissions and Users

### User and Group Management
```bash
whoami              # Display current user
id                  # Display user and group IDs
groups              # Show groups current user belongs to
sudo command        # Execute command as superuser
su username         # Switch to another user
```

### File Permissions
```
-rwxrwxrwx
 │└┬┘└┬┘└┬┘
 │ │  │  └── Permissions for others
 │ │  └───── Permissions for group
 │ └──────── Permissions for owner
 └────────── File type
```

### Permission Management
```bash
chmod 755 file      # Set permissions using octal notation
chmod u+x file      # Add execute permission for user
chown user:group file # Change file owner and group
```

## 5. Standard I/O and Redirection

### Standard Streams
- **stdin (0)**: Standard input
- **stdout (1)**: Standard output
- **stderr (2)**: Standard error

### Redirection
```bash
command > file.txt  # Redirect stdout to file
command >> file.txt # Append stdout to file
command < file.txt  # Use file as stdin
command 2> errors.txt # Redirect stderr to file
command > out.txt 2> err.txt # Separate stdout and stderr
command > file.txt 2>&1 # Redirect both stdout and stderr to file
```

### Pipes
```bash
command1 | command2  # Pipe stdout of command1 to stdin of command2
ls -la | grep ".txt" # List files and filter for .txt files
```

## 6. Practice Exercises

Let's apply what we've learned with a few exercises:

1. **File Navigation**: Create a directory structure with subdirectories and practice navigating between them
2. **Permission Management**: Create files with different permissions and observe how access changes
3. **I/O Redirection**: Practice redirecting output from commands to files and using pipes

Ready to start with any particular section in more detail or would you like to practice with some guided exercises?

# Unix/Linux Basics - Practice Exercises

Since you're already familiar with this material, let's solidify your knowledge with these practical exercises that cover the core concepts. Complete them to ensure you're ready for more advanced topics.

## Exercise Set 1: File System Operations

1. **Directory Hierarchy Challenge**
   ```bash
   # Create this directory structure:
   # project/
   # ├── bin/
   # ├── src/
   # │   ├── main.c
   # │   └── helper.c
   # ├── include/
   # │   └── helper.h
   # └── docs/
   #     └── README.md
   # Then create a symbolic link to README.md in the project root
   ```

2. **File Search and Manipulation**
   - Find all C files (*.c) in your home directory, count them, and save the list to a file
   ans find project -name "*.c" > cfile.txt
   - Create a backup directory and copy all .txt files older than 7 days into it
     find ~/ -name "*.txt" -type f -mtime +7 -exec cp {} ~/backup-textfiles/ \;
     

## Exercise Set 2: Permissions and Users

3. **Permission Management**
   - Create a script file named `secure_script.sh` that prints "This is secure"
   - Set permissions so that:
     - Only you can read, write, and execute it
     - Your group can read and execute but not modify it
     - Others cannot access it at all
       chmod 750 secure_script.sh
   - Create a directory that's readable and executable (but not writable) by everyone
     chmod 555 dirnew

4. **User and Group Practice**
   - List all users on your system and save them to a file
   - Find all files in your home directory owned by a specific user
   - Create a directory that maintains group ownership for new files created within it (sticky bit)

## Exercise Set 3: I/O and Pipes

5. **Redirection Challenges**
   - Create a command that lists all running processes, sorts them by memory usage, and saves the top 10 to a file
   - Write a command that finds all files larger than 10MB, redirecting errors to /dev/null
   - Use redirection to append the output of `date` command to a log file while also displaying it on the screen

6. **Advanced Pipe Usage**
   - Count the number of unique IP addresses in a sample web server log file
   - Find the five largest directories in your home directory
   - Create a pipeline that finds all executable files in /usr/bin, sorts them by size, and displays the 15 largest

## Exercise Set 4: Shell Scripting Integration

7. **Basic Shell Script**
   - Create a shell script that:
     - Takes a directory path as an argument
     - Counts all files by type (extension)
     - Reports disk usage for each file type
     - Saves the report to a file with the current date in its name

8. **Integration Challenge**
   - Write a script that monitors a directory:
     - Creates three directories: `public`, `private`, and `shared`
     - When files are created in the monitored directory, it:
       - Moves text files (.txt) to `public` with read permissions for everyone
       - Moves scripts (.sh) to `private` with execute permissions for owner only
       - Moves all other files to `shared` with read-only permissions for all
     - Creates a log of all operations

## Verification

When you've completed these exercises, you'll have demonstrated proficiency in:
- File system navigation and manipulation
- Understanding and managing permissions
- Using I/O redirection and pipes effectively
- Basic shell scripting

