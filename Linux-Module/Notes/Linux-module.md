# Table of Contents

1. [What is Linux?](#what-is-linux)
2. [What are Linux distributions?](#what-are-linux-distributions?)    
3. [Setting up Linux on your computer](#setting-up-linux-on-your-computer)  
4. [Linux terminal](#linux-terminal)
5. [Linux file system](#linux-file-system)
6. [Linux shortcuts](#linux-shortcuts)
7. [What are Linux commands](#what-are-linux-commands)
8. [Linux Commands](#linux-commands)
    - [File and Directory Management Commands](#file-and-directory-management-commands)
    - [Searching and Filtering](#searching-and-filtering)
    - [User and Group Management Commands](#user-and-group-management-commands)
    - [Displaying User and Group Information](#displaying-user-and-group-information)
    - [Getting Help and Documentation](#getting-help-and-documentation)
    - [System Status and Information](#system-status-and-information)
    - [Networking and Remote Management Commands](#networking-and-remote-management-commands)
    - [Permission and Ownership Commands](#permission-and-ownership-commands)
    - [Downloading Files](#downloading-files)
11. [](#)








## What is Linux?

An open-source, operating system. It’s the backbone of many servers, networks, and cloud infrastructure.

(Linux is open source, which means that anyone can study, modify, and redistribute the source code. This is different from other operating systems, such as Windows and MacOS, which are proprietary)


## What are Linux distributions?

There are many different versions of Linux called distributions (distro).

Linux is the **engine** and distributions are the **vehicle.**

**Ubuntu** is the most beginner-friendly distro.

each distro has its strengths and is suited to different tasks.


## Setting up Linux on your computer

Use virtualization to run Linux/Ubuntu on your operating system.

**Virtual Box** is a free virtualization tool that allows you to run Ubuntu on your OS.


## Linux terminal

The terminal is a command line interface, which allows you to interact with your operating system by typing commands. It gives you direct control of your OS. 

some tasks include:

- navigate through your file system
- install and configure software
- perform a wide range of administrative tasks


## Linux file system

Each directory in the Linux file system has a specific purpose, and together they help the system stay organized and efficient.

- **`/`**: The root of the file system.
- **`/home`**: Where user files are stored.
- **`/bin`, `/sbin`, `/usr/bin`**: Where executable programs are stored.
- **`/etc`**: Configuration files.
- **`/tmp`**: Temporary files.
- **`/var`**: Variable files like logs and caches.

- **`/lib`, `/usr/lib`**: Essential shared libraries and kernel modules.
- **`/boot`**: Contains boot loader files, including the kernel.
- **`/dev`**: Device files representing hardware devices.
- **`/proc`**: Virtual filesystem providing process and kernel information.
- **`/sys`**: Virtual filesystem with information about the system and kernel.
- **`/mnt`**: Mount point for temporarily mounted filesystems.
- **`/media`**: Mount point for removable media like CDs and USB drives.
- **`/root`**: Home directory for the root user.
- **`/opt`**: Optional application software packages.
- **`/srv`**: Data for services provided by the system (e.g., web servers).
- **`/run`**: Runtime data (e.g., system information since the last boot).
  



## Linux shortcuts

How to open up the terminal - **Ctrl Alt T**

Make the writing bigger - **Ctrl Shift +**

Clear the screen - **Ctrl L**

How to exit the typing mode - **Ctrl D**

## **What are Linux commands?**

Textual instructions that tell the OS what to do can be entered directly into the terminal, are case-sensitive, and can include various options and arguments to modify their behavior.

- **_Command_**: `ls`
    - Lists the contents of a directory.
- **_Option_**: `-l`
    - This modifies the behavior of `ls` to display files in a detailed list format (with permissions, owner, size, etc.).
- **_Argument_**: `/home/user/Documents`
    - This specifies the directory you want to list. Without an argument, `ls` would list the contents of the current directory by default.

**The _command_ performs the action.**

**The _options_ modify how the action is performed.**

**The _arguments_ tell the command what files or directories to act on.**

## Linux Commands

## File and Directory Management Commands

These commands are used for navigating directories, managing files, and viewing directory contents.

- **`pwd`**: Displays the full path of the current directory.
- **`cd`**: Changes the directory; **`cd ..`** moves one directory back.
- **`cd ~`**: Navigates to the home directory of the current user.
- **`~`**: Tilde symbol represents the home directory of the current user.
- **`ls`**: Lists files and directories in the current directory.
    - **`ls -a`**: Lists all files, including hidden files (files starting with `.`).
    - **`ls -l`**: Provides detailed file and directory information, including permissions, owner, group, size, and modification time.
    - **`ls -R`**: Lists all files and directories recursively, including subdirectories.
- **`cat`**: Displays the contents of a file or concatenates multiple files.
    - **Example**: `cat file1.txt file2.txt > combined.txt`.
    - **Interactive Mode**: You can use `cat` to create or append content interactively.
- **`echo`**: Displays text or writes it to a file.
    - **Example**: `echo "Hello" > file.txt` (overwrite).
    - **Example**: `echo "Hello" >> file.txt` (append).
- **`touch`**: Creates an empty file or updates the timestamp of an existing file.
    - **Example**: `touch filename.txt`.
    - **Example**: `touch file1.txt file2.txt` (creates multiple files).
- **`cp`**: Copies files from one location to another.
    - **Example**: `cp source_file destination_file`.
    - **`cp -r`**: Copies directories recursively, including all subdirectories and their contents.
        - **Example**: `cp -r source_directory destination_directory`.
- **`mv`**: Moves or renames files or directories.
    - **Example**: `mv old_filename new_filename` (renames a file).
    - **Example**: `mv file.txt /destination_folder` (moves a file).
- **`rm`**: Removes (deletes) files.
    - **`rm -r`**: Deletes directories and their contents recursively.
    - **`rm -rf /`**: Forcefully deletes everything, including the root directory (extremely dangerous).
- **`mkdir`**: Creates a new directory.
    - **`mkdir -p`**: Creates directories along with necessary parent directories.
        - **Example**: `mkdir -p /parent_directory/sub_directory`.
- **`rmdir`**: Removes an empty directory.


