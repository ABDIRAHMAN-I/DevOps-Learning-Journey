# Table of Contents
1. [What is bash?](#what-is-bash)
2. [What is shebang?](#what-is-shebang)
3. [Comments](#comments)
4. [Running scripts from anywhere](#running-scripts-from-anywhere)
5. [Variables](#variables)
6. [Parameters](#parameters)
7. [Arithmetic Expansion](#arithmetic-expansion)
8. [Comparison operators](#comparison-operators)
9. [If statements](#if-statements)
10. [Else and elif](#else-and-elif)
11. [Nested if statements](#nested-if-statements)
12. [While loops](#while-loops)
13. [For loops](#for-loops)
14. [Break and Continue](#break-and-continue)
15. [Functions](#functions)
16. [Handling bad data](#handling-bad-data)
17. [Piping](#piping)
18. [Error Handling](#error-handling)
19. [Exit codes](#exit-codes)
20. [Reading Files](#reading-files)
21. [Script](#script)
22. [Shell](#shell)

## What is bash?
Bash is a shell that's used in Linux, while Linux is an operating system.

- **Bash**
  
  Bash is a command-line shell that's the default in most Linux distributions. It's used for system administration, software development, and network engineering. Bash is easy to learn and can automate tasks. It's also available on macOS and Windows.

- **Linux**

  Linux is an operating system that's free and open source. It has features like multitasking, security, and a graphical user interface (GUI).

### **What is Bash Scripting?**

- **Bash**: A command-line tool to interact with your computer.
- **Bash Script**: A file containing a series of commands you want the computer to execute automatically.

### Why Learn It?

- **Automate tasks**: Save time on repetitive actions.
- **Manage systems**: Handle files, software installs, and system configurations.
- **Boost efficiency**: Get more done with less typing!

## What is shebang?

The **shebang** (`#!`) is a character sequence at the beginning of a script file that tells the operating system which **interpreter** should be used to execute the script. The shebang consists of two characters (`#!`), followed by the path to the interpreter that should be used. Example: `#!/bin/bash`

An **interpreter** is a type of computer program that **executes code** written in a programming or scripting language directly, without the need for prior compilation into machine language (binary code). Examples of interpreters are Bash shell, Python, etc.

### **Example of shebang**

The **shebang** specifies the interpreter for the script, allowing you to run the script directly without needing to manually invoke the interpreter each time. If a script file is made executable and contains a shebang line, the script can be run as a standalone program.

For example, with a script `myscript.sh` that has the following contents:

```bash
#!/bin/bash
echo "Hello, World!"
```

You can make it executable:

```bash
chmod +x myscript.sh
```

And then run it directly:

```bash
./myscript.sh
```

## Comments

In **Bash** (Bourne Again SHell) scripting, comments are used to explain or document code, making it easier for others (or yourself) to understand the script. Bash ignores any comments during execution.

### **Single-Line Comments**
A single-line comment starts with a `#` symbol. Everything after `#` on that line is treated as a comment and ignored by the Bash interpreter.

Example:

```bash
# This is a comment
echo "Hello, World!"  # This comment is after a command
```

### **Multi-Line Comments**
Bash does not have a built-in multi-line comment syntax like some other languages. However, you can simulate multi-line comments by using `#` on each line, or by using a `: ' ... '` trick.

Example using multiple `#` symbols:

```bash
# This is a comment
# that spans
# multiple lines
```

Example using a `:` and a block of text:

```bash
: '
This is a multi-line comment.
You can use this method to comment
out several lines of code at once.
'
```

## Running scripts from anywhere

### **How to run a script from anywhere without specifying its PATH**

To run a script from **anywhere** in your system without specifying its full path or use `./` or even `bash`, you need to add the script to a directory that is included in your system’s **`PATH`**.

### **Why PATH directory?**
Because the path is an environment variable that tells the shell which directories to search for executable files in response to commands.

### **Steps to Run Script from Anywhere**

1. **Move the Script to a Directory in the `PATH`**

   Directories like `/usr/local/bin`, `/usr/bin`, and `/bin` are typically included in the `PATH` variable. By placing your script in one of these directories, you can run it from any location.

   ```bash
   sudo mv myscript.sh /usr/local/bin
   ```

2. **Make sure the script is executable**

   ```bash
   chmod +x /usr/local/bin/myscript.sh
   ```

3. **Run the script from anywhere**

   ```bash
   myscript.sh
   ```

## Variables

Variables allow you to store and manipulate data. You can assign values to variables and reference them later in the script or in the shell session. Bash variables can store numbers, strings, and arrays.

### **How to Create Variables**

1. Create a file using `vim` filename.sh
2. Start with shebang `#!/bin/bash`
3. Assign variable: `greeting="Hello World"`
4. To access the variable, use: `$greeting`
5. To echo the value stored in greeting: `echo $greeting`
6. Save and exit file
7. Give file executable permissions: `chmod +x filename.sh`
8. Call variable: `./filename.sh`

**Examples**:
- **String**: `greeting="Hello World"`
- **Numbers**: `count=42`
- **Arrays**: `fruits=("apple" "banana" "kiwi")`

### **Variable Interpolation**

Variable interpolation allows you to dynamically embed variable values in strings.

Example:

```bash
name="Ahmed"
echo "Hello, $name"
```

Output: `Hello, Ahmed`

## Parameters

**Parameters** are entities that store values. They can represent variables, special values, or arguments passed to a script or function. Understanding parameters is crucial for writing flexible and dynamic shell scripts.

### **Using Parameters**

```bash
#!/bin/bash

echo "Parameter 1: $1"
echo "Parameter 2: $2"
echo "Parameter 3: $3"
```

**Input**

Values passed on the command line will be substituted into the script's parameter variables `$1`, `$2`, and `$3`.

```bash
./script.sh hello hi everyone
```

**Output**

```bash
Parameter 1: hello
Parameter 2: hi
Parameter 3: everyone
```

### **Combine All Parameters at Once**

```bash
#!/bin/bash

echo "All parameters: $@"
```

**Input**

```bash
./script.sh hello hi everyone
```

**Output**

```bash
All parameters: hello hi everyone
```

## Arithmetic Expansion

**Arithmetic expansion** allows you to perform mathematical calculations in Bash.

### **Example 1**

```bash
#!/bin/bash

num1=5
num2=10
result=$((num1 + num2))

echo "The sum of $num1 and $num2 is: $result"
```

**Output**: `The sum of 5 and 10 is: 15`

### **Example 2**

```bash
#!/bin/bash

length=5
width=8
area=$((length * width))
perimeter=$((2 * (length + width)))

echo "Rectangle area: $area"
echo "Rectangle perimeter: $perimeter"
```

**Output**:
- Rectangle area: 40
- Rectangle perimeter: 26

## Comparison operators

### **1. Numeric Comparison Operators**

These operators are used to compare integers in Bash.

| Operator | Description                  | Example                     |
|----------|------------------------------|-----------------------------|
| `-eq`    | Equal to                     | `[ "$a" -eq "$b" ]`         |
| `-ne`    | Not equal to                 | `[ "$a" -ne "$b" ]`         |
| `-lt`    | Less than                    | `[ "$a" -lt "$b" ]`         |
| `-le`    | Less than or equal to        | `[ "$a" -le "$b" ]`         |
| `-gt`    | Greater than                 | `[ "$a" -gt "$b" ]`         |
| `-ge`    | Greater than or equal to     | `[ "$a" -ge "$b" ]`         |

### **2. String Comparison Operators**

These operators compare strings in Bash.

| Operator | Description       | Example                          |
|----------|-------------------|----------------------------------|
| `=`      | Equal to          | `[ "$str1" = "$str2" ]`          |
| `!=`     | Not equal to      | `[ "$str1" != "$str2" ]`         |
| `-z`     | String is empty   | `[ -z "$str" ]`                  |
| `-n`     | String is not empty | `[ -n "$str" ]`                |

### **3. File Comparison Operators**

These operators are used to compare file attributes.

| Operator | Description                    | Example                      |
|----------|--------------------------------|------------------------------|
| `-e`     | File exists                    | `[ -e file.txt ]`            |
| `-f`     | File is a regular file         | `[ -f file.txt ]`            |
| `-d`     | Directory exists               | `[ -d /path/to/directory ]`  |
| `-s`     | File is not empty              | `[ -s file.txt ]`            |
| `-r`     | File is readable               | `[ -r file.txt ]`            |
| `-w`     | File is writable               | `[ -w file.txt ]`            |
| `-x`     | File is executable             | `[ -x file.sh ]`             |
| `-nt`    | Newer than (file comparison)   | `[ file1 -nt file2 ]`        |
| `-ot`    | Older than (file comparison)   | `[ file1 -ot file2 ]`        |

### **4. Logical Operators (Combining Comparisons)**

You can combine multiple conditions using logical operators.

| Operator | Description                                | Example                                    |
|----------|--------------------------------------------|--------------------------------------------|
| `&&`     | Logical AND (both conditions must be true) | `[ "$a" -gt 5 ] && [ "$b" -lt 10 ]`      |
| `||`     | Logical OR (either condition may be true)  | `[ "$a" -gt 5 ] || [ "$b" -lt 10 ]`      |
| `!`      | Logical NOT (negates the condition)        | `[ ! -e file.txt ]` (true if file does not exist) |

## If Statements

`if` statements are used to perform conditional operations. The structure of an `if` statement in Bash is fairly straightforward but flexible, allowing for complex conditional logic.

### Usage Example

```bash
#!/bin/bash

age=25

if [ $age -gt 18 ]; then
    echo "You are an adult!"
fi
```

**Output**: `You are an adult!` (because 25 is greater than 18)

### If Statements with Logical Operators

```bash
#!/bin/bash

grade=85

if [ $grade -ge 90 ] && [ $grade -le 100 ]; then
    echo "Excellent!"
fi
```

### If Statements with Strings

```bash
#!/bin/bash

name="Alice"

if [ "$name" == "Alice" ]; then
    echo "Hello, Alice"
fi
```

## Else and Elif

The `else` statement is used in conjunction with `if` to specify a block of code that will be executed if the `if` condition evaluates to `false`. Essentially, if the condition in the `if` block is not met, the `else` block will run.

### Usage Example

```bash
#!/bin/bash

num=10

if [ "$num" -gt 5 ]; then
    echo "The number is greater than 5"
else
    echo "The number is less than or equal to 5"
fi
```

### Elif Statement

`elif` stands for "else if" and is used to check multiple conditions in an `if` statement. When the first `if` condition is false, the `elif` block allows you to test additional conditions before reaching the final `else` block (if present). You can have multiple `elif` blocks, and they are evaluated sequentially from top to bottom.

### Usage Example

```bash
#!/bin/bash

num=15

if [ "$num" -gt 20 ]; then
    echo "The number is greater than 20"
elif [ "$num" -gt 10 ]; then
    echo "The number is greater than 10 but less than or equal to 20"
elif [ "$num" -gt 5 ]; then
    echo "The number is greater than 5 but less than or equal to 10"
else
    echo "The number is 5 or less"
fi
```

## Nested If Statements

A **nested if statement** in **Bash** is when one `if` statement is placed inside another `if`, `elif`, or `else` block. This allows for more complex logic by enabling the script to check conditions within conditions.

### Usage Example

```bash
age=25
gender="female"

if [ "$age" -ge 18 ]; then
    echo "You are an adult."
    if [ "$gender" == "male" ]; then
        echo "You are an adult male."
    else
        echo "You are an adult female."
    fi
else
    echo "You are a minor."
fi
```

## While Loops

A `while` loop repeatedly executes a block of code as long as the given condition evaluates to `true`. This is useful when you need to perform repetitive tasks until a certain condition is met.

### Usage Example

```bash
#!/bin/bash

count=1

while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

### While Loops with Arrays

```bash
#!/bin/bash

# Declare an array
fruits=("apple" "banana" "cherry" "date")

# Initialize an index
index=0

# Get the length of the array
array_length=${#fruits[@]}

# While loop to iterate over the array
while [ $index -lt $array_length ]; do
    echo "Fruit: ${fruits[$index]}"
    index=$((index + 1))  # Increment the index
done
```

**Explanation**:
- **Array Declaration**: `fruits=("apple" "banana" "cherry" "date")` creates an array called `fruits`.
- **Index**: We initialize `index=0` to start at the first element.
- **Array Length**: `${#fruits[@]}` gives the total number of elements in the array.
- The `while` loop runs as long as the index is less than the array length.
- On each iteration, the loop prints the current element of the array and then increments the index by 1.

## For Loops

`for` loops are used to iterate over a list of items, which could be numbers, strings, or array elements. They offer a convenient way to perform repetitive tasks and can be more straightforward than `while` loops for certain types of iteration.

### Usage Example

```bash
#!/bin/bash

for (( i = 1; i <= 5; i++ )); do
    echo "Number: $i"
done
```

### For Loops with Arrays

```bash
#!/bin/bash

# Declare an array
colors=("red" "blue" "green" "yellow")

# Loop through array elements
for color in "${colors[@]}"; do
    echo "Color: $color"
done
```

## Break and Continue

`break` and `continue` are control flow statements used within loops to manage how the loop behaves.

### **1.  `break` Statement**

The `break` statement is used to exit a loop early. It terminates the loop when a certain condition is met, and the control moves to the next statement outside the loop.

### **Example: Using `break` to Exit a Loop**

```bash
#!/bin/bash

for (( i=1; i<=5; i++ )); do
    if [ $i -eq 3 ]; then
        break
    fi
    echo "Number: $i"
done
```

### **Script Breakdown**

```bash
#!/bin/bash
```
- **Shebang**: This line tells the system that the script should be run using the `bash` shell.

```bash
for (( i=1; i<=5; i++ ))
```
- **For Loop Initialization**: This line starts a `for` loop with C-style syntax.
    - `i=1`: Initializes the loop variable `i` to 1.
    - `i<=5`: The loop will continue as long as `i` is less than or equal to 5.
    - `i++`: After each iteration, `i` is incremented by 1.

```bash
do
```
- **Start of Loop Body**: This keyword begins the block of code that will be executed in each iteration of the loop.

```bash
if [ $i -eq 3 ]; then
    break
fi
```
- **If Statement**: This condition checks if the current value of `i` is equal to 3.
    - `[ $i -eq 3 ]`: This is a test condition checking if `i` is equal to 3.
    - `break`: If the condition is true, the `break` command is executed, which exits the `for` loop immediately. This means the loop will terminate and no further iterations will occur.

```bash
echo "Number: $i"
```
- **Echo Command**: This line prints the current value of `i` to the terminal.
    - `"Number: $i"`: The string "Number: " followed by the current value of `i` is printed.

```bash
done
```
- **End of Loop Body**: This keyword marks the end of the `for` loop block.

### **2. `continue` Statement**

The `continue` statement skips the current iteration of the loop and moves on to the next iteration, without exiting the loop.

```bash
#!/bin/bash

for (( i=1; i<=5; i++ )); do
    if [ $i -eq 3 ]; then
        continue
    fi
    echo "Number: $i"
done
```

## Functions

Functions are a way to group a series of commands into a single unit. Functions allow you to reuse code, make scripts more modular, and improve readability. They can take parameters, return values, and be called multiple times from different parts of your script.

### **1. Defining a Function**

To define a function in Bash, use the following syntax:

```bash
function_name() {
    # Commands to execute
}
```

### **Calling a Function**

Once defined, you can call the function by simply using its name followed by parentheses:

```bash
function_name
```

### **Usage Example**

```bash
#!/bin/bash

# Define a function
greet() {
    echo "Hello, $1!"
}

# Call the function
greet "Alice"
```

**Output**: `Hello, Alice!`

### **Functions with Parameters**

Functions can accept parameters, allowing you to pass data to the function and use it within its code. Parameters are passed to functions in the form of positional arguments, which can be accessed using `$1`, `$2`, `$3`, and so on. You can also use `$@` to refer to all arguments and `$#` to get the number of arguments.

- `$0` - This special variable contains the name of the script (or function) being executed.
- `$1` - This special variable holds the value of the first argument passed to the function.
- `$2` - This special variable holds the value of the second argument passed to the function.
- `$@` - This line prints all the arguments passed to the function.
- `$#` - This special variable holds the number of arguments passed to the function.

```bash
#!/bin/bash

print_args() {
    echo "Number of arguments: $#"
    echo "Script name: $0"
    echo "First argument: $1"
    echo "Second argument: $2"
    echo "All arguments: $@"
}

print_args "Tom" "Ali"
```

**Output**:
- Number of arguments: 2
- Script name: bash
- First argument: Tom
- Second argument: Ali
- All arguments: Tom Ali

### **Function with User Inputs**

You can write functions that prompt users for input, process that input, and then return results or perform actions based on it.

```bash
#!/bin/bash
greet_user() {
    echo "What is your name?"
    read name
    echo "Hello, $name!"
}

greet_user
```

### **Functions with Default Values**

```bash
#!/bin/bash
greet() {
    local name
    if [ $# -eq 0 ]; then
        echo "What is your name?"
        read name
    else
        name="$1"
    fi
    echo "Hello, $name!"
}

greet
```

## Handling Bad Data

### **Validate User Inputs**

```bash
validate_age() {
    local age=$1

    if [[ ! $age =~ ^[0-9]+$ ]]; then
        echo "Invalid age. Please provide a numeric value."
        return 1
    fi

    if (( age < 18 )); then
        echo "Sorry, you must be at least 18 years old."
        return 1
    fi

    echo "Congratulations! You are eligible."
    return 0
}
```

### **Sanitize Strings**

```bash
sanitize_string() {
    local input=$1
    local sanitized_input=${input//[^a-zA-Z0-9]/}
    echo "$sanitized_input"
}

# Calling the "sanitize_string" function
echo "Please enter a username:"
read input_username

sanitized_username=$(sanitize_string "$input_username")

echo "Sanitized username: $sanitized_username"
```

## Piping

Piping is a powerful feature in Unix-like operating systems, including Linux and macOS, that allows you to direct the output of one command directly into another command. This is achieved using the pipe symbol `|`. Piping enables you to create complex command sequences and streamline data processing by chaining commands together.

### **Example 1: Get File Count**

```bash
get_file_count() {
    local directory="$1"
    local file_count
    file_count=$(ls "$directory" | wc -l)
    echo "Number of files in $directory: $file_count"
}

get_file_count "./"
```

### **Example 2: Search Logs**

```bash
search_logs() {
    local search_term="$1"
    grep "$search_term" logs.txt | awk '{ print $2 }'
}

search_logs "ERROR"
```

## Error Handling

```bash
#!/bin/bash

num1=10
num2=0

if [ $num2 -eq 0 ]; then
    echo "Error: division by zero is not allowed"
    exit 1
fi

result=$((num1 / num2))
echo "The result is: $result"
```

### **Error Handling in Scripts**

```bash
#!/bin/bash

FILE="/nonexistent"

if [[ -f "$FILE" ]]; then
    echo "File exists"
else
    echo "File does not exist."
fi
```

## Exit Codes

**Exit codes** in Bash (and in many other programming environments) are numeric values returned by a program or script when it finishes executing. They indicate whether the program ran successfully or encountered an error. These codes help other scripts or programs understand what happened during execution and can be used for troubleshooting.

### **Key Points About Exit Codes**

1. **Success (Exit Code 0)**:
    - If a program or command runs successfully, it returns an exit code of **0**.
    - `0` is universally understood as "success" in most Unix-like systems.
    - `echo $?` - used to check the exit code of the last executed command.

```bash
ls
echo $?
```

### **Fixing Commands with Exit Codes**

```bash
#!/bin/bash

command -v git 2>/dev/null

if [[ $? -ne 0 ]]; then
    echo "git is not installed. Please install git."
    exit 1
else
    echo "git is installed"
fi
```

## Using `set` Commands Together

- **`set -e`**: Immediately exit if any command has a non-zero exit status.
- **`set -u`**: Treat unset variables as an error and exit immediately.
- **`set -x`**: Print each command before executing it, useful for debugging.
- **`set -eux`**: Combine these options to create robust, well-debugged scripts.

## Reading Files

### **Reading Files Using Simple Redirection**

```bash
#!/bin/bash

read_file() {
    local file_path="$1"
    while IFS= read -r line; do
        echo "$line"
    done < "$file_path"
}

read_file "./log.txt"
```

## Script

A **script** is a set of instructions written in a programming or scripting language that automates tasks or performs a sequence of operations. Scripts are typically used to automate repetitive tasks, configure systems, process data, or manage software applications.

**./** - is a notation used to specify the current directory. It’s commonly used to run executable files or scripts located in the current directory.

## Shell

**What is the shell?**

A user interface that provides access to the OS services. It takes Linux commands and makes the computer do what we want, allowing you to communicate with your OS.

**What is bash?**

There are many types of shells, but the most common type is called **bash** (born again shell). Think of it as a language.

### **Shell Types**

1. **Bash Shell**
2. **Zsh Shell**
3. **Ksh Shell**
4. **Fish Shell**
5. **Csh/Tcsh Shell**

### **How to Determine Your Shell**

Use the command:

```bash
echo $SHELL
```

### **Zsh Shell**

To switch to zsh in the terminal, just type `zsh`, and to switch back to bash, type `bash`.

To make zsh your default shell, use:

```bash
chsh -s /bin/zsh
```

To customize your zsh, use:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

To apply changes after configuring, use:

```bash
source .zshrc
```

Press **i** to get into insert mode, and to save changes, press **:wq!**.
