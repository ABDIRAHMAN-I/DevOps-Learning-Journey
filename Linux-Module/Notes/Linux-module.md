# Table of Contents
1. [What is Linux?](#what-is-linux)
    - [What are Linux distributions?](#what-are-linux-distributions?)    
    - [Setting up Linux on your computer](#setting-up-linux-on-your-computer)  
    - [Linux terminal](#linux-terminal)
2. [Linux file system](#linux-file-system)
3. [Linux shortcuts](#linux-shortcuts)
4. [Linux Commands](#linux-commands)
    - [What are Linux commands](#what-are-linux-commands)
    - [File and Directory Management Commands](#file-and-directory-management-commands)
5. [](#)
6. [](#)
7. [](#)
8. [](#)  
9. [](#)
10. [](#)
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

## Linux Commands

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

## File and Directory Management Commands

- **`ls`**: View the contents of the current directory.
    - **`ls -a`**: List all files and directories, including hidden files (files or directories starting with a dot (`.` will not appear with a regular `ls` command)).
    - **`ls -l`**: Provide detailed information about files and directories, including:
        - Permissions
        - Owner
        - Group
        - Size
        - Modification time
        - More
    - **`ls -R`**: List all files and directories recursively, including all subdirectories and their contents, to show the directory structure in detail. It’s useful for understanding the hierarchy and contents of directories in more detail.
- **`cp`**: Copies files or directories. Cannot copy directories. **`cp`** [file_you_want_to_copy] source destination
    - **`cp -r`** - copies **directories** and their contents from one location to another.  **`cp -r`** [directory_you_want_to_copy] source destination
- **`mv`**: Moves or renames files or directories. *rename: **`mv`** (old_filename) (new_filename)* / *move: **`mv`** (file_you_want_to_move) (directory_you_want_to move_it_to)*
- **`rm`**: Removes (deletes) files.
    - **`rm -r`:** used to remove (delete) directories.
    - **`rm -rf` /** - Deletes Everything. **extremely dangerous** and should never be run carelessly
    
    **`rm`**: Stands for "remove" and is used to delete files or directories.
    
    **`r`**: The recursive flag, meaning it will delete the directory and all of its contents, including subdirectories and their contents.
    
    **`f`**: The force flag, which suppresses warnings and forces the deletion of files, even if they are write-protected.
    
    **`/`**: The root directory, which is the top-level directory of the entire file system.
- **`mkdir` `[make_directory]`**: Creates a new directory.
    - **`mkdir -p [directory_path]`**: Create a directory and any necessary parent directories.
- **`rmdir`**: Removes an empty directory.
- **`touch`**: Creates an empty file or updates the timestamp of an existing file. ex:**`touch`** filename.txt.
This will create a new, empty file named filename.txt in the current directory. If the file already exists, it simply updates its last modified and last accessed timestamps without changing the content. You can also create multiple empty files at once by listing them after **`touch`**  file1.txt  file2.txt  file3.txt
