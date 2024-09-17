# Table of Contents
1. [What is bash?](#what-is-bash)
2. [What is shebang?](#what-is-shebang)
3. [Comments](#comments)
4. [Linux Commands](#linux-commands)
6. [Running scripts from anywhere](#running-scripts-from-anywhere)
7. [Variables](#variables)
8. [Parameters](#parameters)  
9. [Arithmetic Expansion](#arithmetic-expansion)
10. [Comparison operators](#comparison-operators)
11. [If statements](#if-statements)
12. [](#)



## What is bash?

Bash is a shell that's used in Linux, while Linux is an operating system

- **Bash**

Bash is a command-line shell that's the default in most Linux distributions. It's used for system administration, software development, and network engineering. Bash is easy to learn and can automate tasks. It's also available on macOS and Windows.

- **Linux**

Linux is an operating system that's free and open source. It has features like multitasking, security, and a graphical user interface (GUI).

### **What is Bash Scripting?**

- **Bash**: A command-line tool to interact with your computer.
- **Bash Script**: A file containing a series of commands you want the computer to execute automatically.

### Why Learn It?

- **Automate tasks**: Save time on repetitive actions.
- **Manage systems**: Handle files, software installs, and system configurations.
- **Boost efficiency**: Get more done with less typing!


## What is shebang?

**(**`#!`) - A **shebang** (also called a "hashbang") is a character sequence at the beginning of a script file that tells the operating system which **interpreter** should be used to execute the script. The shebang consists of two characters, followed by the path to the interpreter that should be used. `#!/bin/bash`

An **interpreter** is a type of computer program that **executes code** written in a programming or scripting language directly, without the need for prior compilation into machine language (binary code). Examples of interpreters are like, bash shell, python, etc.

Instead of converting the entire program into machine code at once (as a compiler does), an interpreter reads, translates, and executes the code line-by-line or instruction-by-instruction.

### **Example of shebang**

The **shebang** specifies the interpreter for the script, allowing you to run the script directly without needing to manually invoke the interpreter each time. If a script file is made executable and contains a shebang line, the script can be run as a standalone program.

For example, with a script `myscript.sh` that has the following contents:

```bash
bash

#!/bin/bash
echo "Hello, World!"

```

You can make it executable:

```bash
bash

chmod +x myscript.sh

```

And then run it directly:

```bash
bash

./myscript.sh

```

