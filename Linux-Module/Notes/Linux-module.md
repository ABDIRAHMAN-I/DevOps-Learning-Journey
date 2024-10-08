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
9. [Data Redirection](#data-redirection)
10. [Environment Variables](#environment-variables)
11. [Vim Mode](#vim-mode)   
   
    








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

# Data Redirection

In Linux, **standard streams** refer to three primary channels used for input and output during the execution of programs. These are:

1. **standard input (stdin)** - 
- This is the default stream from which a program reads its input. Typically, it refers to the keyboard, but it can also be redirected to read from files or other input sources.
- Example: `cat` reads from `stdin` by default

1. **standard output (stdout**) - 
- This is the default stream to which a program writes its output. Typically, it refers to the terminal or console. You can redirect `stdout` to files or other destinations.
- Example: Writing the output of a command to a file

1. **standard error (stderr)** - 
- This stream is used for error messages or diagnostics. Like `stdout`, it normally goes to the terminal but can be redirected independently of `stdout`.
- Example: Redirecting error messages to a separate file.

### Redirection:

- **Redirect stdout** to a file: `command > file`
- **Redirect stderr** to a file: `command 2> file`
- **Redirect both stdout and stderr** to the same file: `command > file 2>&1`
- **Read input from a file**: `command < file`


# Environment Variables

In Linux, environment variables are key-value pairs used to configure the system and control program behavior. they are are used to store information like:

- user preferences
- system paths
- configuration settings

They allow users to customize various settings like the default editor, language preferences, or the `PATH` for finding executable files. 

Common variables include `PATH`, `HOME`, and `USER`. They can be set temporarily in a session using the `export` command or made permanent by adding them to configuration files like `~/.bashrc`. 

Environment variables are useful for tasks such as managing application versions, setting network proxies, and automating scripts. For instance, they help define database credentials, configure debugging tools, or specify which web browser or language settings the system should use by default. This flexibility makes environment variables essential for both system configuration and efficient workflow management.

The `printenv` command is used to display the environment variables and their values for the current shell session.

By running this command, you can see all the variables that are currently set, including system variables like `PATH`, `HOME`, and user-defined variables.

The `env` command is very similar to `printenv`, but `env` also has additional functionality for manipulating the environment when running a command.

- `printenv` is primarily used for displaying environment variables.
- `env` can display environment variables **and** also modify the environment for running a command.

The `export` command in Linux is used to set environment variables or make existing shell variables available to child processes. 

Once a variable is exported, it is passed on to any program or script run from that shell session.

The `$` symbol is used to **reference** or **access the value** of a variable.

## **Difference between non-exported and exported**

### 1. **Normal (Non-exported) Variable**:

- A normal variable is only available within the current shell (the current session or shell environment).
- It is **not** passed to child processes (such as scripts or commands executed from the shell).
- It exists only in the shell where it was defined.

### Example:

`MY_VAR`="Hello World"
`echo $MY_VAR`  # Output: Hello World
`./my_script.sh`  # The script cannot access MY_VAR

In this case, `MY_VAR` is only available in the current shell. If you try to access `MY_VAR` inside a script or child process (like `my_script.sh`), it won’t be recognized because it hasn't been exported.

### 2. **Exported Variable**:

- An exported variable is not only available in the current shell, but it is also passed on to any child processes (programs or scripts) run from that shell.
- Exporting makes the variable part of the environment for all sub-processes.

### Example:

`export MY_VAR`="Hello World"
`echo $MY_VAR`  # Output: Hello World
`./my_script.sh`  # The script can access MY_VAR

### Setting permanent **Variables**:

modify Zsh's configuration files, by adding your variable at the bottom and saving it.

- open your Zsh configuration file: `vim` .zshrc
- then go to the bottom of the file and enter insert mode: `O`this will do both for you
- save the file and exit: `:wq!`
- then finally to set permanently: `source` .zshrc

The `unset` command in Linux is used to remove variables or functions from the shell environment. When you use `unset` on a variable, it removes it from the environment, meaning it is no longer accessible in the current shell session or any child processes.

`MY_VAR`="Hello"
`echo` $MY_VAR   # Output: Hello
`unset` MY_VAR
`echo` $MY_VAR   # No output (variable is unset)

### Adding a Directory to `PATH`

1. **Check the current value of `PATH`**:

`echo` $PATH

Each directory listed is a location where the system will search for executables. In this example:

- `/usr/local/sbin`
- `/usr/local/bin`
- `/usr/sbin`
- `/usr/bin`
- `/sbin`
- `/bin`

1. **Append a new directory to `PATH`**:
Use `:` as a separator when adding new paths to `PATH`. Here's an example of appending `/usr/local/mydir` to the existing `PATH`:

`export` PATH="${PATH}:/usr/local/mydir”

1. **Verify the change**:
After appending, check if the new path is added:

`echo` $PATH

## Alias

An **alias** is a shortcut or a shorthand command that you create to simplify or customize your command line experience. Aliases allow you to define new commands or shorten existing ones by associating them with longer or more complex commands.

**Creating an Alias**:

- You can create an alias using the `alias` command followed by the name you want for the alias and the command it should run.

syntax: `alias` alias_name='command_to_run’ 

or if I want it to read something: `alias` alias_name=’echo”what_to_read”’ 

if I want to save it permanently, use the same method as before:

- open your Zsh configuration file: `vim` .zshrc
- then go to the bottom of the file and enter insert mode: `O`this will do both for you
- save the file and exit: `:wq!`
- then finally to set permanently: `source` .zshrc

**Change PATH Permanently**

how to make a script run from any directory 

come back to this one when you have time

**Standard enviroment variables** 

how to access the values of enviroment variable:

#!/bin/bash

echo “Executable paths: $PATH”

echo “Default language: $LANG”

**assigning enviroment variable to local variables** makes our code more readable and easier to work with. example:

### **Example:**

Let's say you have an environment variable named `HOME` that stores the home directory path, and you want to use this value multiple times in a script.

### Without local variables:

```bash
bash
Copy code
#!/bin/bash

echo "Home directory: $HOME"
cd $HOME/projects
mkdir $HOME/projects/new_project
echo "New project directory created at $HOME/projects/new_project"

```

In this example, `$HOME` is used multiple times directly, which can make the code harder to manage if you need to use other environment variables or perform complex logic. Let's improve it using a local variable.

### With local variables:

```bash
bash
Copy code
#!/bin/bash

# Assign environment variable to a local variable
home_dir="$HOME"

echo "Home directory: $home_dir"
cd "$home_dir/projects"
mkdir "$home_dir/projects/new_project"
echo "New project directory created at $home_dir/projects/new_project"

```

### **Benefits:**

1. **Readability**: Using a more descriptive local variable (like `home_dir`) makes it easier to understand the context of the variable throughout the script.
2. **Consistency**: If the environment variable changes, you only need to modify it in one place.
3. **Maintainability**: If you have multiple environment variables or complex logic, assigning them to local variables reduces repetition and improves maintainability.


# Vim mode


**command mode** - used for deleting text or copying lines. 

*moving around the text - left (H), right (L), down (J), up (K),* 

*beginning of the line (0), end of the line ($)*

*to jump to a specific line press **:(num)** the number you want*

*search for a particular word press **/(word)** followed by the word you want*

*if there are multiple word with the same name press **n** for the next word with the same name.*

*to delete an entire line press **dd*** 

*to delete a letter press **x***

*to copy a letter press **y***

*to copy a line press **yy***

*to cut a line press **dd***

*to delete the section after the curser capital **D***

*to paste text press **p***

*press **u** to undo*

*to start a new line and enter insert mode press **o***

*press **Ctrl r** to redo last change*

*to set numbers for each line press **:set number**  and to exit press **:set nonumber***

*to enable syntax highlighting press **:syntax on** and to turn off press **:syntax off***

*Press **Esc** to exit each mode*

*to save your work type the following, **:wq! w** = write (i.e save) and **q** = quit, sometimes it doesn't let you so you have to overide it by using the **!*** 

*if you don't want to save changes and just quit without saving type **:q!***

*if you want to save changes and not quit **:w***

**insert mode** - used to insert and edit text. Press **i** to enter this mode 

**visual mode** - used for selecting text in a visual format. press **v**  to enter this mode





