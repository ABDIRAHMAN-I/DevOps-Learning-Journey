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








# What is Linux?

An open-source, operating system. It’s the backbone of many servers, networks, and cloud infrastructure.

(Linux is open source, which means that anyone can study, modify, and redistribute the source code. This is different from other operating systems, such as Windows and MacOS, which are proprietary)


# What are Linux distributions?

There are many different versions of Linux called distributions (distro).

Linux is the **engine** and distributions are the **vehicle.**

**Ubuntu** is the most beginner-friendly distro.

each distro has its strengths and is suited to different tasks.


# Setting up Linux on your computer

Use virtualization to run Linux/Ubuntu on your operating system.

**Virtual Box** is a free virtualization tool that allows you to run Ubuntu on your OS.


# Linux terminal

The terminal is a command line interface, which allows you to interact with your operating system by typing commands. It gives you direct control of your OS. 

some tasks include:

- navigate through your file system
- install and configure software
- perform a wide range of administrative tasks


# Linux file system

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
  



# Linux shortcuts

How to open up the terminal - **Ctrl Alt T**

Make the writing bigger - **Ctrl Shift +**

Clear the screen - **Ctrl L**

How to exit the typing mode - **Ctrl D**

# **What are Linux commands?**

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

# Linux Commands

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

## Searching and Filtering

These commands are used to search for text patterns within files or filter output.

- **`grep`**: Searches for patterns or specific text in a file.
    - **Example**: `grep "pattern" filename`.

## **User and Group Management Commands**:

These commands manage users, groups, and their permissions, as well as perform administrative tasks.

- **`sudo`**: Executes commands with superuser (root) privileges.
    - **Example**: `sudo command`.
- **`sudo su`**: Switches to the root user for performing multiple administrative tasks.
    - **Example**: `sudo su` (use `exit` to return to normal user).
- **`su`**: Switches to another user account.
    - **Example**: `su - username`.
- **`sudo usermod -aG (groupname) (username)`**: Adds a user to a group.
    - **Example**: `sudo usermod -aG sudo alice`.
- **`sudo deluser (user) sudo`**: Removes a user from the `sudo` group.
    - **Example**: `sudo deluser alice sudo`.
- **`sudo groupadd (name of group)`**: Creates a new group.
    - **Example**: `sudo groupadd developers`.
- **`sudo groupdel (groupname)`**: Deletes a group.
    - **Example**: `sudo groupdel developers`.
- **`sudo gpasswd -d (username) (groupname)`**: Removes a user from a group.
    - **Example**: `sudo gpasswd -d alice developers`.
- **`sudo useradd (username)`**: Creates a new user account.
    - **Example**: `sudo useradd bob`.
- **`sudo passwd (username)`**: Sets or changes the password for a user.
    - **Example**: `sudo passwd bob`.

## Displaying User and Group Information

These commands provide information about users, groups, and permissions.

- **`groups`**: Displays the groups a user belongs to.
    - **Example**: `groups username`.
- **`whoami`**: Displays the current logged-in user.
    - **Example**: `whoami`.
- **`id`**  :  Displays user or group ID
    - **Example**: `id` [OPTION] [USERNAME]

## Getting Help and Documentation
These commands provide help, documentation, and detailed information about other commands.

- **`man`**: Displays the manual pages for a command, providing detailed usage and options.
    - **Example**: `man ls`.

## System Status and Information
These commands provide information about system environment and process status.

- **`echo $PATH`**: Displays the directories where executable files are searched for by the system.
- bash - to switch to bash

## Networking and Remote Management Commands
These commands deal with networking and managing systems over a network.

- **`ssh`**: Securely logs into a remote machine.
    - **Example**: `ssh username@remote_host`
- **`scp`**: Securely copies files between hosts.
    - **Example**: `scp file.txt username@remote_host:/path/to/destination`
- **`ping`**: Helps you test if a device is reachable and how fast the connection is.
    - **Example**: `ping (IP address or domain)`
    - If it keeps running and you want to stop it, press **Ctrl + C**.
- **`curl`**: Transfers data from or to a server.
    - **Example**: `curl https://example.com`
- **`traceroute`**: shows the path data takes from your computer to a destination, displaying each hop (step) such as routers and servers along the way to its destination.
    - **Example**: `traceroute (IP address or domain)`
- **`nslookup`**: is a tool that helps you find the **IP address** of a website (domain) or the **website** that matches an IP address.
    - **Example**: `nslookup example.com`
- **`dig`**: Performs detailed DNS queries, returning various DNS records like IP addresses or mail servers for a domain.
    - **Example**: `dig example.com`

These commands are often used together in network management, file transfers, or remote system management.


## Permission and Ownership Commands

These commands are used to manage who can access, modify, or execute files and directories.

- **`chmod`**: Changes the permissions of files and directories.

       usage example: `chmod` [who][operator][permissions] [filename]

**`[who]`**: One or more of `u`, `g`, `o`, or `a`.

**`[operator]`**: `+`, ``, or `=`.

**`[permissions]`**: One or more of `r`, `w`, or `x`.

**`[filename]`**: The file or directory to modify.

### Permissions Overview:

**`r`**: Read permission.

**`w`**: Write permission.

**`x`**: Execute permission.

### Permission Groups:

**`u`**: User (the file owner).

**`g`**: Group (users who belong to the file's group).

**`o`**: Others (all other users).

**`a`**: All (applies to `u`, `g`, and `o`).

### Symbolic Operators:

**`+`**: Adds a permission.

`-`: Removes a permission.

**`=`**: Sets the exact permission, replacing the previous permissions.

### 

- **`chown`**: Changes the ownership of a file or directory.
    
    usage example: `chown` [options] [new_owner][:new_group] file_or_directory
    
    **`new_owner`**: The new owner (user) of the file or directory.
    
    **`new_group`**: The new group of the file or directory.
    
    **`file_or_directory`**: The file or directory whose ownership is being changed.
    
     **`options`**: Additional options, such as recursive changes.
    
- **`chown -R`** - used to **recursively change the ownership** of files and directories, including all subdirectories and files within the specified directory. The `-R` option stands for **recursive**, meaning it applies the ownership change to every file and subdirectory under the given directory.
- **`chgrp`**: Changes the group ownership of a file or directory.
    
    usage example: `chgrp` [options] new_group file_or_directory
    
    **`new_group`**: The name of the new group that you want to assign to the file or directory.
    
    **`file_or_directory`**: The file or directory whose group ownership you want to change.
    
    **`options`**: Various options to control how `chgrp` behaves (like recursive changes).
    

### **Numeric Format (Octal)**

Permissions can be represented numerically. Each permission is assigned a value:

- **Read (`r`)**: 4
- **Write (`w`)**: 2
- **Execute (`x`)**: 1

The total numeric value represents the permissions for **Owner**, **Group**, and **Others**. For example:

- **7 (rwx)**: Full permission (read, write, execute).
- **6 (rw-)**: Read and write only.
- **5 (r-x)**: Read and execute only.
- **0 (---)**: No permissions.

### Example: Setting Permissions Numerically

To give the **owner full permissions**, the **group read and execute permissions**, and **others read-only** permissions, you would use:

```bash
bash
Copy code
chmod 754 filename

```

Explanation:

- **7 (rwx)**: Owner has read, write, and execute permissions.
- **5 (r-x)**: Group has read and execute permissions.
- **4 (r--)**: Others have read-only permission.

### **Symbolic Format**

In symbolic format, you specify the user category and the permission you want to set:

- **u**: User (owner)
- **g**: Group
- **o**: Others
- **a**: All (user, group, others)

You can add (`+`), remove (`-`), or set (`=`) specific permissions.

### Example: Setting Permissions Symbolically

To give the **owner write permissions**, and remove execute permissions for **group and others**:

```bash
bash
Copy code
chmod u+w,go-x filename

```

Explanation:

- **u+w**: Adds write permission for the owner.
- **go-x**: Removes execute permissions for group and others.

**Make a file executable**:

```bash
bash
Copy code
chmod +x script.sh

```

- This gives everyone execute permission for `script.sh`.
- **Set full permissions for the owner and read-only for others**:
    
    ```bash
    bash
    Copy code
    chmod 744 myfile.txt
    
    ```
    
    - Owner gets read, write, execute (`rwx`), and others get read-only (`r--`).
- **Remove write permissions for everyone**:
    
    ```bash
    bash
    Copy code
    chmod a-w filename
    
    ```
    
    - This removes write permission for all users (owner, group, and others).


## Downloading files

- **`curl`**: A tool to transfer data from or to a server, using various protocols such as HTTP, FTP, and more. It is commonly used for interacting with APIs.
    - **Example**: `curl https://example.com`
- **`wget`**: A command-line utility for downloading files from the web. It supports downloading files via HTTP, HTTPS, and FTP, and is great for handling large files and recursive downloads.
    - **Example**: `wget https://example.com/file.zip`











