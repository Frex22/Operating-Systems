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
