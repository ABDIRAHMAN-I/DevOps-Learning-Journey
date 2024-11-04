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
## Comments 

In **Bash** (Bourne Again SHell) scripting, comments are used to explain or document code, making it easier for others (or yourself) to understand the script. Bash ignores any comments during execution.

**Syntax for Comments in Bash:**

1. **Single-Line Comments**:
A single-line comment starts with a **`#`** symbol. Everything after `#` on that line is treated as a comment and ignored by the Bash interpreter.
    
    Example:
    
    ```bash
    bash
    # This is a comment
    echo "Hello, World!"  # This comment is after a command
    
    ```
    
2. **Multi-Line Comments**:
Bash does not have a built-in multi-line comment syntax like some other languages. However, you can simulate multi-line comments by using `#` on each line, or by using a `: ' ... '` trick.
    
    Example using multiple `#` symbols:
    
    ```bash
    bash
    
    # This is a comment
    # that spans
    # multiple lines
    
    ```
    
    Example using a `:` and a block of text:
    
    ```bash
    bash
    
    : '
    This is a multi-line comment.
    You can use this method to comment
    out several lines of code at once.
    '
    
    ```
## Running scripts from anywhere

**How to run a script from anywhere without specifying its PATH**

To run a script from **anywhere** in your system without specifying its full path or use ./ or even bash, you need to add the script to a directory that is included in your system’s **`PATH`**

**Why PATH directory?**

because the path is an environment variable that tells the shell which directories to search for executable files in response to commands.

**step 1. Move the Script to a Directory in the `PATH`**

Directories like `/usr/local/bin`, `/usr/bin`, and `/bin` are typically included in the `PATH` variable. By placing your script in one of these directories, you can run it from any location.

```bash
bash

sudo mv myscript.sh /usr/local/bin

```

**step 2. Make sure the script is executable:** also note you can add any name after it to make it easier when you're calling that script.

```bash
bash

chmod +x /usr/local/bin/myscript.sh

```

**step 3. After moving the script to `/usr/local/bin`, you can run it from anywhere**

```bash
bash

myscript.sh

```
## Variables

variables allow you to store and manipulate data. You can assign values to variables and reference them later in the script or in the shell session. Bash variables can store numbers, strings, and arrays. 

**How to create variables:**

step 1 - create a file using `vim` filename.sh

step 2 - then start with shebang #! /bin/bash

step 3 - assign variable. greeting=”Hello World”

step 4 - to access the variable use: $greeting

step 5 - if you want the echo command to output the value stored in greeting: echo $greeting

step 6 - save and exit file

step 7 - give file executable commands: chmod +x filename.sh

step 8 - call variable: ./filename.sh

string: greeting=”Hello World”

numbers: count=42

arrays: fruits=(”apple”, “banana”, “kiwi”)

**variable interpolation**

allows you to dynamically embed variable values in strings.

name=”Ahmed”

echo “Hello, $name”

output: Hello, Ahmed


## Parameters

**parameters** are entities that store values. They can represent variables, special values, or arguments passed to a script or function. Understanding parameters is crucial for writing flexible and dynamic shell scripts.

#!/bin/bash

`echo` “parameter 1:  $1”

`echo` “parameter 2:  $2”

`echo` “parameter 3:  $3”

input

the values passed on the command line will be substituted into the scripts parameter variables $1,$2, and $3

./script.sh hello hi everyone

output

parameter 1: hello

parameter 1: hi

parameter 1: everyone 

how to combine all parameter at once

#!/bin/bash

`echo` “parameter 1:  $1”

`echo` “parameter 2:  $2”

`echo` “parameter 3:  $3”

`echo` “all parameters: $@”

input

the values passed on the command line will be substituted into the scripts parameter variables $1,$2, and $3

./script.sh hello hi everyone

output

parameter 1: hello hi everyone

## Arithmetic Expansion

mathematical calculations 

**example 1**

#!/bin/bash

num1=5

num=10

result=$((num1 + num2))

echo “the sum of $num1 and $num2 is: $result”

output

the sum of 5 and 10 is: 15

**example 2**

#!/bin/bash

length=5

width=8

area=$((length * width))

perimeter=$((2 * (length + width)))

echo “Rectangle area: $area”

echo “Rectangle perimeter: $perimeter”

output

Rectangle area: 40 

Rectangle perimeter: 26

### Arithmetic Expansion with (parameters)

allows us to take input from the user or from command line arguments and perfom calculations based on those values.

length=”$1”

width=”$2”

area=$((length * width))

perimeter=$((2 * (length + width)))

echo “Rectangle area: $area”

echo “Rectangle perimeter: $perimeter”

output

Rectangle area: answers will be based on numbers the user provides

Rectangle perimeter: answers will be based on numbers the user provides

## Comparison operators

### **1. Numeric Comparison Operators**

These operators are used to compare integers in Bash.

| Operator | Description | Example |  |
| --- | --- | --- | --- |
| `-eq` | Equal to | `[ "$a" -eq "$b" ]` (true if `$a` equals `$b`) |  |
| `-ne` | Not equal to | `[ "$a" -ne "$b" ]` (true if `$a` does not equal `$b`) |  |
| `-lt` | Less than | `[ "$a" -lt "$b" ]` (true if `$a` is less than `$b`) |  |
| `-le` | Less than or equal to | `[ "$a" -le "$b" ]` (true if `$a` is less than or equal to `$b`) |  |
| `-gt` | Greater than | `[ "$a" -gt "$b" ]` (true if `$a` is greater than `$b`) |  |
| `-ge` | Greater than or equal to | `[ "$a" -ge "$b" ]` (true if `$a` is greater than or equal to `$b`) |  |

### **2. String Comparison Operators**

These operators compare strings in Bash.

| Operator | Description | Example |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| `=` | Equal to | `[ "$str1" = "$str2" ]` (true if `$str1` equals `$str2`) |  |  |  |  |
| `!=` | Not equal to | `[ "$str1" != "$str2" ]` (true if `$str1` does not equal `$str2`) |  |  |  |  |
| `-z` | String is empty | `[ -z "$str" ]` (true if string is empty) |  |  |  |  |
| `-n` | String is not empty | `[ -n "$str" ]` (true if string is not empty) |  |  |  |  |

### **3. File Comparison Operators**

These operators are used to compare file attributes.

| Operator | Description | Example |  |  |
| --- | --- | --- | --- | --- |
| `-e` | File exists | `[ -e file.txt ]` (true if the file exists) |  |  |
| `-f` | File is a regular file | `[ -f file.txt ]` (true if the file is a regular file) |  |  |
| `-d` | Directory exists | `[ -d /path/to/directory ]` (true if the directory exists) |  |  |
| `-s` | File is not empty | `[ -s file.txt ]` (true if the file is not empty) |  |  |
| `-r` | File is readable | `[ -r file.txt ]` (true if the file is readable) |  |  |
| `-w` | File is writable | `[ -w file.txt ]` (true if the file is writable) |  |  |
| `-x` | File is executable | `[ -x file.sh ]` (true if the file is executable) |  |  |
| `-nt` | Newer than (file comparison) | `[ file1 -nt file2 ]` (true if `file1` is newer than `file2`) |  |  |
| `-ot` | Older than (file comparison) | `[ file1 -ot file2 ]` (true if `file1` is older than `file2`) |  |  |

### **4. Logical Operators (Combining Comparisons)**

You can combine multiple conditions using logical operators.

| Operator | Description | Example |
| --- | --- | --- |
| `&&` | Logical AND (both conditions must be true) | `[ "$a" -gt 5 ] && [ "$b" -lt 10 ]` |
| ` |  | ` |
| `!` | Logical NOT (negates the condition) | `[ ! -e file.txt ]` (true if file does not exist) |



## If statements

`if` statements are used to perform conditional operations. The structure of an `if` statement in Bash is fairly straightforward but flexible, allowing for complex conditional logic.

`if` [ condition ]; then
# code to execute if condition is true
`fi`

usage example

#! /bin/bash

age=25

if [ $age -gt 18]

then

echo “You are an adult! ”

output

You are an adult! #because 25 is greater than 18

**if statements with logical operators** 

usage example 

#! /bin/bash

grade=85

if [ $grade -ge 90] && [ $grade -le 100]

then

echo “Excellent!”

fi

**if statements with strings** 

usage example 

#! /bin/bash

name=”Alice”

if [ “$name” == “Alice”]

then

echo “Hello, Alice” 

fi

## Else and elif

the `else` statement is used in conjunction with `if` to specify a block of code that will be executed if the `if` condition evaluates to `false`. Essentially, if the condition in the `if` block is not met, the `else` block will run.

if [ condition ]; then
# code to execute if condition is true
else
# code to execute if condition is false
fi

usage example

#!/bin/bash

num=10

if [ "$num" -gt 5 ]; then
echo "The number is greater than 5"
else
echo "The number is less than or equal to 5"
fi

**elif statement**

`elif` stands for "else if" and is used to check multiple conditions in an `if` statement. When the first `if` condition is false, the `elif` block allows you to test additional conditions before reaching the final `else` block (if present). You can have multiple `elif` blocks, and they are evaluated sequentially from top to bottom.

if [ condition1 ]; then
# code if condition1 is true
elif [ condition2 ]; then
# code if condition2 is true
elif [ condition3 ]; then
# code if condition3 is true
else
# code if none of the conditions are true
fi

usage example

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

## Nested if statements

A **nested if statement** in **Bash** is when one `if` statement is placed inside another `if`, `elif`, or `else` block. This allows for more complex logic by enabling the script to check conditions within conditions.

if [ condition1 ]; then
# code if condition1 is true
if [ condition2 ]; then
# code if condition2 is also true
else
# code if condition2 is false
fi
else
# code if condition1 is false
fi

usage example

age=25
gender="female"

if [ "$age" -ge 18 ]; then

echo "You are an adult."

 if [ “$gender” = “male”  ]; then

echo “You are an adult male.”

else

echo “You are an adult female”

fi

else
echo "You are a minor."
fi


## While loops

a `while` loop repeatedly executes a block of code as long as the given condition evaluates to `true`. This is useful when you need to perform repetitive tasks until a certain condition is met.

while [ condition ]; do
# Code to execute while condition is true
done

#!/bin/bash

count=1

while [ $count -le 5 ]; 

do
     echo "Count: $count"
     count=((count + 1))
done

while loops with arrays

#!/bin/bash

**#Declare an array**

fruits=("apple" "banana" "cherry" "date")

**#Initialize an index**

index=0

**#Get the length of the array**

array_length=${#fruits[@]}

**#While loop to iterate over the array**

while [ $index -lt $array_length ]; 

do
    echo "Fruit: ${fruits[$index]}"
    index=$((index + 1))  # Increment the index
done

### **Explanation:**

- **Array Declaration**: `fruits=("apple" "banana" "cherry" "date")` creates an array called `fruits`.
- **Index**: We initialize `index=0` to start at the first element.
- **Array Length**: `${#fruits[@]}` gives the total number of elements in the array.
- The `while` loop runs as long as the index is less than the array length.
- On each iteration, the loop prints the current element of the array and then increments the index by 1.


## For loops

`for` loops are used to iterate over a list of items, which could be numbers, strings, or array elements. They offer a convenient way to perform repetitive tasks and can be more straightforward than `while` loops for certain types of iteration.

for item in item1 item2 item3; do
# Code to execute for each item
done

for (( i = start; i <= end; i++ )); do
# Code to execute for each value of i
done

usage example

#!/bin/bash

for (( i = 1; i <= 5; i++ )); do
echo "Number: $i"
done

#!/bin/bash

**#Declare an array**

colors=("red" "blue" "green" "yellow")

**#Loop through array elements**

for color in "${colors[@]}"; do
echo "Color: $color"
done


## Break and Continue

`break` and `continue` are control flow statements used within loops to manage how the loop behaves.

### **1.  `break` Statement**

The `break` statement is used to exit a loop early. It terminates the loop when a certain condition is met, and the control moves to the next statement outside the loop.

### **Example: Using `break` to Exit a Loop**

#!/bin/bash

for (( i=1; i<=5 i++))

do

if [ $i -eq 3 ]

then

break

fi

echo “Number: $i”

done

### **Script Breakdown**

```bash
bash
Copy code
#!/bin/bash

```

- **Shebang**: This line tells the system that the script should be run using the `bash` shell.

```bash
bash
Copy code
for (( i=1; i<=5; i++ ))

```

- **For Loop Initialization**: This line starts a `for` loop with C-style syntax.
    - `i=1`: Initializes the loop variable `i` to 1.
    - `i<=5`: The loop will continue as long as `i` is less than or equal to 5.
    - `i++`: After each iteration, `i` is incremented by 1.

```bash
bash
Copy code
do

```

- **Start of Loop Body**: This keyword begins the block of code that will be executed in each iteration of the loop.

```bash
bash
Copy code
     if [ $i -eq 3 ]
     then
          break
     fi

```

- **If Statement**: This condition checks if the current value of `i` is equal to 3.
    - `[ $i -eq 3 ]`: This is a test condition checking if `i` is equal to 3.
    - `break`: If the condition is true, the `break` command is executed, which exits the `for` loop immediately. This means the loop will terminate and no further iterations will occur.

```bash
bash
Copy code
echo "Number: $i"

```

- **Echo Command**: This line prints the current value of `i` to the terminal.
    - `"Number: $i"`: The string "Number: " followed by the current value of `i` is printed.

```bash
bash
Copy code
done

```

- **End of Loop Body**: This keyword marks the end of the `for` loop block.

### **2. `continue` Statement**

The `continue` statement skips the current iteration of the loop and moves on to the next iteration, without exiting the loop.

#!/bin/bash

for (( i=1; i<=5 i++))

do

if [ $i -eq 3 ]

then

continue

fi

echo “Number: $i”

done

### **Scenario: Monitoring System Health**

Imagine you are running a script to monitor various system health metrics, such as CPU usage or disk space, across several servers. Each server is identified by an index number, and you want to check the health of these servers sequentially. However, if you encounter a particular server that fails or exhibits critical issues, you want to stop further checks immediately to avoid wasting resources or encountering unnecessary errors.

### **Example Script**

```bash
bash
Copy code
#!/bin/bash

# List of server indices to monitor
for (( i=1; i<=5; i++ ))
do
    # Simulate a health check command
    health_status=$(./check_server_health.sh $i)

    # Check if the server is critical
    if [[ "$health_status" == "CRITICAL" ]]; then
        echo "Critical issue detected on server $i. Stopping further checks."
        break
    fi

    echo "Server $i is healthy."
done

```

### **Explanation**

1. **Initialization**: The loop iterates through server indices from 1 to 5.
2. **Health Check Simulation**: `./check_server_health.sh $i` simulates a command that checks the health of the server with index `$i`. The command's output is stored in the variable `health_status`.
3. **Critical Check**: If `health_status` is "CRITICAL" (indicating a serious issue), the `break` command is triggered, stopping further iterations of the loop.
4. **Output**: If the server is healthy, a message is printed indicating that the server is okay. If a critical issue is found, a message is printed, and the loop is exited.

### **Real-Life Impact**

- **Efficiency**: By using `break`, the script avoids unnecessary checks on subsequent servers if a critical issue is found early. This saves time and computational resources.
- **Immediate Action**: Detecting and stopping after a critical issue ensures that no further checks are done that could compound or escalate the problem.
- **Focused Monitoring**: The script allows for immediate intervention and focused monitoring, preventing issues from propagating.



## Functions

functions are a way to group a series of commands into a single unit. Functions allow you to reuse code, make scripts more modular, and improve readability. They can take parameters, return values, and be called multiple times from different parts of your script.

### **1. Defining a Function**

To define a function in Bash, use the following syntax:

function_name() {
# Commands to execute
}

### **Calling a Function**

Once defined, you can call the function by simply using its name followed by parentheses:

function_name

**usage example**

#!/bin/bash

**Define a function**

greet() {
echo "Hello, $1!"
}

**Call the function**

greet "Alice"

output

Hello, Alice!

**Functions with parameters**

functions can accept parameters, allowing you to pass data to the function and use it within its code. Parameters are passed to functions in the form of positional arguments, which can be accessed using `$1`, `$2`, `$3`, and so on. You can also use `$@` to refer to all arguments and `$#` to get the number of arguments.

$0 - This special variable contains the name of the script (or function) being executed.

$1 - This special variable holds the value of the first argument passed to the function.

$2 - This special variable holds the value of the second argument passed to the function.

$@ - This line prints all the arguments passed to the function.

$# - This special variable holds the number of arguments passed to the function.

#!/bin/bash

`print_args`() {

echo “Number of arguments: $#”

echo “Script name: $0”

echo “First argument: $1”

echo “Second argument: $2”

echo “All aruguments: $@”

}
`print_args` ”Tom” “Ali”

#call command 

`print_args` ”Tom” “Ali”

output

print_args ”Tom” “Ali”
“Number of arguments: 2”
“Script name: bash”
“First argument: ”Tom””
“Second argument: “Ali””
“All aruguments: ”Tom” “Ali””

**function with user inputs** 

you can write functions that prompt users for input, process that input, and then return results or perform actions based on it. 

#!/bin/bash

greet_user () {

echo “What is your name?”

read name

echo “hello, $name!”

}

greet_user 

```bash
bash
Copy code
greet_user () {

```

- **Function Definition**: This line defines a function named `greet_user`. The `()` indicates that it is a function. Everything between the curly braces `{}` is the code that will run when the function is called.

```bash
bash
Copy code
echo “What is your name?”

```

- **Prompt**: This line prints a message to the terminal asking the user for their name.

```bash
bash
Copy code
read name

```

- **User Input**: The `read` command waits for the user to type something and then stores the input in a variable named `name`. Whatever the user enters is saved in this variable.

```bash
bash
Copy code
echo “hello, $name!”

```

- **Greeting**: This line prints a greeting using the value of the `name` variable. The `$name` syntax is used to refer to the value stored in the `name` variable. If the user entered "Alice," it would output: `hello, Alice!`.

```bash
bash
Copy code
}

```

- **End of Function**: The closing curly brace `}` marks the end of the `greet_user` function.

```bash
bash
Copy code
greet_user

```

- **Function Call**: This line calls the `greet_user` function, meaning the function’s code will be executed. The script will prompt the user for their name and then greet them based on the input.

### **Example Run:**

```csharp
csharp
Copy code
What is your name?
Alice
hello, Alice!

```

- The script first prints `What is your name?`.
- The user inputs `Alice`, and the script responds with `hello, Alice!`.

#!/bin/bash

greet() {

local name 

if [ $# -eq 0 ]; then 

echo “What is your name?”

read name 

else

name=”$1”

fi

echo “hello, $name!”

}

greet

```bash
greet() {

```

- **Function Definition**: This defines a function named `greet`. The code within the curly braces `{}` will run when the function is called.

```bash
bash
Copy code
local name

```

- **Local Variable**: The `local` keyword limits the scope of the `name` variable to the `greet` function. This means that `name` can only be used inside this function and won't affect or be affected by variables outside the function.

```bash
bash
Copy code
if [ $# -eq 0 ]; then

```

- **Condition for Arguments**: The `if` statement checks if no arguments were passed to the function. The special variable `$#` represents the number of arguments passed to the script or function. If it's equal to `0`, it means no arguments were passed, so the script will ask the user for their name.

```bash
bash
Copy code
echo “What is your name?”
read name

```

- **User Input**: If no arguments are passed to the function, it prompts the user with "What is your name?" and waits for the user to input their name using the `read` command. The entered name is stored in the `name` variable.

```bash
bash
Copy code
else
name="$1"
fi

```

- **Argument Handling**: If an argument is passed to the function, it skips the prompt and uses the value of `$1` (the first argument) as the name. The `$1` refers to the first argument provided to the function.

```bash
bash
Copy code
echo “hello, $name!”

```

- **Greeting**: The script prints a greeting using the value of `name`. If no argument was provided, it will use the value from the `read` command. If an argument was passed, it will use that value.

```bash
bash
Copy code
}

```

- **End of Function**: The closing curly brace marks the end of the `greet` function.

```bash
bash
Copy code
greet

```

- **Function Call**: This calls the `greet` function. Since no argument is provided here, the script will prompt the user for their name.

---

### **Behavior of the Script:**

### **Scenario 1: No Argument Passed**

If you run the script without passing any arguments, the function will prompt the user for their name.

```bash
bash
Copy code
$ ./script.sh
What is your name?
Alice
hello, Alice!

```

- The script asks "What is your name?" and waits for user input.
- After the user inputs "Alice," the script responds with "hello, Alice!".

### **Scenario 2: Argument Passed**

If you modify the script to pass an argument to the function, it will greet the user without prompting them for their name.

```bash
bash
Copy code
greet "Bob"

```

- When the function is called with an argument (`"Bob"`), it uses that name directly.

```bash
bash
Copy code
$ ./script.sh
hello, Bob!

```

## Handling bad data 

Validate user inputs 

```
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

```bash
validate_age() {

```

- **Function Definition**: This defines a function named `validate_age`. The code between the curly braces `{}` will run when the function is called.

```bash
bash
Copy code
local age=$1

```

- **Local Variable**: The function takes one argument (passed to `$1`), which is assumed to be the user's age. This value is stored in a local variable `age`. The `local` keyword ensures the variable `age` is only used within the function.

```bash
bash
Copy code
if [[ ! $age =~ ^[0-9]+$ ]]; then
    echo "Invalid age. Please provide a numeric value."
    return 1
fi

```

- **Numeric Validation**:
    - `[[ ! $age =~ ^[0-9]+$ ]]` checks if `age` is not a valid numeric value.
    - The regular expression `^[0-9]+$` ensures that `age` consists only of digits (`0-9`) with no other characters.
    - If the input is not a number, the function outputs `"Invalid age. Please provide a numeric value."` and returns `1`, indicating failure.

```bash
bash
Copy code
if (( age < 18 )); then
    echo "Sorry, you must be at least 18 years old."
    return 1
fi

```

- **Age Validation**:
    - `(( age < 18 ))` checks if the `age` is less than 18.
    - If `age` is under 18, the function prints `"Sorry, you must be at least 18 years old."` and returns `1`, indicating failure.

```bash
bash
Copy code
echo "Congratulations! You are eligible."
return 0

```

- **Success Case**:
    - If the `age` is numeric and 18 or above, the function outputs `"Congratulations! You are eligible."` and returns `0`, indicating success.

Input sanitization 

```visual-basic
sanitize_string() {
    local input=$1
		local sanitized_input=${input//[^a-zA-Z0-9]/}
    
     echo "$sanitized_input"
        
}

#callin the "sanitize_string" function
echo "please enter a username:"
read input_username

sanitized_username=$(sanitize_string "$input_username")

echo "sanitized username: $sanitized_username"

```

### **Breakdown of the Code:**

```bash
bash
Copy code
sanitize_string() {
    local input=$1
    local sanitized_input=${input//[^a-zA-Z0-9]/}

    echo "$sanitized_input"
}

```

- **Function Definition (`sanitize_string()`)**: The function accepts a single argument (`$1`) and assigns it to a local variable `input`.
- **Sanitizing Input (`${input//[^a-zA-Z0-9]/}`)**: This is where the "sanitization" happens.
    - `${input//[^a-zA-Z0-9]/}`: This is a string replacement operation in Bash.
        - `[^a-zA-Z0-9]` is a regular expression that matches any character **that is not** a letter (`a-z` or `A-Z`) or a digit (`0-9`).
        - The replacement pattern `//` removes those characters, leaving only alphanumeric characters.
    - The sanitized result is stored in the variable `sanitized_input`.
- **Output Sanitized String**: The sanitized input is echoed back to wherever the function is called.

### **Calling the Function:**

```bash
bash
Copy code
echo "please enter a username:"
read input_username

```

- **Prompt for Username**: The script prompts the user to input a username.

```bash
bash
Copy code
sanitized_username=$(sanitize_string "$input_username")

```

- **Call to `sanitize_string`**: The entered username is passed to the `sanitize_string` function, and the sanitized result is captured in the variable `sanitized_username`.

```bash
bash
Copy code
echo "sanitized username: $sanitized_username"

```

- **Display the Sanitized Username**: The script prints the sanitized version of the username to the console.

### **How It Works:**

1. The user is prompted to enter a username.
2. The `sanitize_string` function is called with the entered username as an argument.
3. The function removes any non-alphanumeric characters from the input and returns the sanitized result.
4. The script then displays the sanitized username to the user.

### **Example:**

### Input:

```css
css
Copy code
please enter a username:
John_Doe@2023

```

### Output:

```yaml
yaml
Copy code
sanitized username: JohnDoe2023

```

In this example, the underscores (`_`), `@` symbol, and any other non-alphanumeric characters are removed, leaving just `JohnDoe2023`.

### **Real-World Use:**

This kind of function can be useful when validating user inputs for usernames, file names, or any other fields that should only contain alphanumeric characters. It's common to sanitize inputs to prevent issues like special characters causing problems with databases, file systems, or security vulnerabilities.


## piping 

Piping is a powerful feature in Unix-like operating systems, including Linux and macOS, that allows you to direct the output of one command directly into another command. This is achieved using the pipe symbol `|`. Piping enables you to create complex command sequences and streamline data processing by chaining commands together.

**example 1** 

get_file_count() {

local directory=”$1”

local file_count

file_count=$(ls “$directory” | wc -l)

echo “number of files in $directory: $file_count”

}

get_file_count “./”

This script defines a function `get_file_count()` that counts the number of files in a specified directory and then prints that count. Here’s a detailed breakdown:

### **Script Breakdown**

```bash
bash
Copy code
get_file_count() {
    local directory="$1"
    local file_count

```

- **Function Definition**: The `get_file_count` function is defined to take a single argument, which is the directory whose file count you want to determine.
- **Local Variables**:
    - `directory` stores the directory path passed as an argument.
    - `file_count` will store the result of the file count calculation.

```bash
bash
Copy code
    file_count=$(ls "$directory" | wc -l)

```

- **Count Files**:
    - `ls "$directory"`: Lists the contents of the directory specified by the `directory` variable.
    - `| wc -l`: Pipes the output of `ls` to `wc -l`, which counts the number of lines. Each line corresponds to a file or directory name.
    - The result is assigned to the `file_count` variable.

```bash
bash
Copy code
    echo "Number of files in $directory: $file_count"
}

```

- **Output**: Prints the number of files in the specified directory along with a descriptive message.

```bash
bash
Copy code
get_file_count “./”

```

- **Function Call**: Calls the `get_file_count` function with the argument `./`, which represents the current directory. Note that the double quotes around `./` should be standard quotes (`"`) and not typographic quotes (`“”`).

### **How It Works:**

1. **Function Invocation**: The function `get_file_count` is called with the current directory (`./`) as its argument.
2. **List Files**: The function executes `ls ./`, which lists all files and directories in the current directory.
3. **Count Files**: The output of `ls` is piped to `wc -l` to count the number of lines, which gives the number of files and directories.
4. **Print Result**: The function then prints the count along with a message.

### **Example:**

Assume the current directory (`./`) contains:

- `file1.txt`
- `file2.txt`
- `subdir1`

Running the function with `get_file_count "./"` would produce:

```jsx
javascript
Copy code
Number of files in ./ : 3

```

**example 2** 

search_logs() {

local search_term=”$1”

grep “$search_term” logs.txt | awk ‘{ print $2 }

}

search_logs “ERROR”

### **Script Breakdown**

```bash
bash
Copy code
search_logs() {
    local search_term="$1"
    grep "$search_term" logs.txt | awk '{ print $2 }'
}

```

### **1. Function Definition:**

- **`search_logs()`**: This defines a function named `search_logs`.
- **`local search_term="$1"`**:
    - `local` declares a local variable inside the function.
    - `search_term` is assigned the first argument (`$1`) passed to the function when it's called. In this case, the argument will be "ERROR" (from the function call `search_logs "ERROR"`).

### **2. Command Execution:**

```bash
bash
Copy code
grep "$search_term" logs.txt | awk '{ print $2 }'

```

- **`grep "$search_term" logs.txt`**:
    - The `grep` command searches for occurrences of the value stored in `search_term` (in this case, "ERROR") inside the file `logs.txt`. It finds all lines that contain the word "ERROR".
- **`|`** (Pipe):
    - The pipe (`|`) takes the output of `grep` (all lines in `logs.txt` that contain "ERROR") and sends it to the `awk` command for further processing.
- **`awk '{ print $2 }'`**:
    - `awk` is a text-processing tool that works on each line of input.
    - `{ print $2 }` tells `awk` to print the second field (or column) of each line. Fields in `awk` are separated by whitespace by default.

### **3. Function Call:**

```bash
bash
Copy code
search_logs "ERROR"

```

- **`search_logs "ERROR"`**: Calls the `search_logs` function with "ERROR" as the argument. This argument is passed as `search_term` inside the function, so it searches for "ERROR" in `logs.txt`.

### **How It Works:**

1. The function is called with the search term `"ERROR"`.
2. Inside the function, `grep` searches for lines in `logs.txt` that contain the word "ERROR".
3. The resulting lines are passed to `awk`, which prints the second field (word) from each matching line.
4. The output is the second word from each line in `logs.txt` that contains "ERROR".

### **Example:**

Assume `logs.txt` contains the following:

```yaml
yaml
Copy code
INFO 1234 User logged in
ERROR 5678 Disk space low
ERROR 9123 Network timeout
INFO 4567 Process started

```

When the function is called with `search_logs "ERROR"`, it performs the following:

- **`grep "ERROR" logs.txt`**:
This command would output:
    
    ```vbnet
    vbnet
    Copy code
    ERROR 5678 Disk space low
    ERROR 9123 Network timeout
    
    ```
    
- **`awk '{ print $2 }'`**:
This command would print the second field (the numbers `5678` and `9123`) from the matching lines:
    
    ```yaml
    yaml
    Copy code
    5678
    9123
    
    ```
    

### **Points to Consider:**

- The script will only print the second field (word or column) from each line that contains the search term.
- You need to ensure that `logs.txt` exists in the current directory where you are running the script.
- The fields in `logs.txt` are assumed to be separated by spaces. If the format of the file is different, you might need to adjust the `awk` command accordingly.

## Error Handling

#!/bin/bash

the script will crash and throw an error because 10 cant be divided by 0. If this was a long script an unhandled error could cause the entire script to stop leading to significant problems.

num1=10

num2=0

results=$((num1/ num2))

echo “the result is: $result”

**how to deal with errors like this**

#!/bin/bash

num1=10

num2=0

if  [ $num2 -eq 0]; then 

echo “Error: division by zero is not allowed”

exit 1

fi

results=$((num1/ num2))

echo “the result is: $result”

output

Error: division by zero is not allowed

now we have a meaningful error messege and the script stops without crashing.

**Error handling in scripts** 

#!/bin/bash

FILE=”/nonexistent”

if [[ -f “$FILE” ]]; then 

echo “File exists”

else

echo “File does not exist.”

fi

This script checks if a file (in this case, `"/nonexistent"`) exists and whether it's a regular file (not a directory, symbolic link, etc.). Based on the result, it prints a corresponding message.

### **Script Breakdown**

```bash
bash
Copy code
FILE="/nonexistent"

if [[ -f "$FILE" ]]; then
    echo "File exists"
else
    echo "File does not exist."
fi

```

### **1. File Variable:**

```bash
bash
Copy code
FILE="/nonexistent"

```

- This assigns the string `"/nonexistent"` to the variable `FILE`.
- `"/nonexistent"` is just an example file path, and in this case, it refers to a file that likely doesn't exist.

### **2. `if` Condition:**

```bash
bash
Copy code
if [[ -f "$FILE" ]]; then

```

- **`[[ -f "$FILE" ]]`**:
    - `[[ ... ]]`: This is a conditional expression used to test conditions in `bash`.
    - -`f "$FILE"`: This checks if the path stored in the variable `FILE` (in this case `"/nonexistent"`) refers to a **regular file**.
    - The `-f` flag in a Bash script is used to check if a given file exists and is a regular file (as opposed to a directory or other special file types like symbolic links, block devices, etc.).
        - It evaluates to **true** if the file exists and is a regular file (not a directory, block device, or other type).
        - It evaluates to **false** if the file doesn't exist or isn't a regular file.

### **3. If the Condition is True:**

```bash
bash
Copy code
echo "File exists"

```

- If `[[ -f "$FILE" ]]` returns true (i.e., the file exists and is a regular file), the script prints **"File exists"**.

### **4. Else Block (If the Condition is False):**

```bash
bash
Copy code
else
    echo "File does not exist."

```

- If the file doesn't exist or isn't a regular file, the script enters the `else` block and prints **"File does not exist."**

### **5. End of the `if` Statement:**

```bash
bash
Copy code
fi

```

- `fi` marks the end of the `if-else` statement in Bash.


## Exit codes

**Exit codes** in Bash (and in many other programming environments) are numeric values returned by a program or script when it finishes executing. They indicate whether the program ran successfully or encountered an error. These codes help other scripts or programs understand what happened during execution and can be used for troubleshooting.

### **Key Points About Exit Codes:**

1. **Success (Exit Code 0):**
    - If a program or command runs successfully, it returns an exit code of **0**.
    - `0` is universally understood as "success" in most Unix-like systems.
    - echo $? - used to check the exit code of the last executed command

❯`ls`
Desktop   Documents  'Personal Vault.lnk'   desktop.ini   [greet.sh](http://greet.sh/)   [my-first-script.sh](http://my-first-script.sh/)  'practice folder'
❯ `echo` $?
0

`ls` code ran with no issues so when i checked the exit code it came back 0 meaning success.

❯ `nonexistentcommand`
zsh: command not found: nonexistentcommand
❯ `echo` $?
127

`nonexistentcommand` code ran but is invalid and dosent exist so the exit code came back 127

**now lets fix this** 

#!/bin/bash

command -v git 2>/dev/null

if [[ $? -ne 0 ]]; then 

echo “git is not installed. please install git.”

exit 1

else

echo “git is installed”

fi

This Bash script checks whether Git is installed on the system by using the `command -v git` command. If Git is not installed, the script informs the user and exits with a non-zero exit code (1). If Git is installed, it prints a success message.

### **Script Breakdown:**

```bash
bash
Copy code
command -v git 2>/dev/null

```

- **`command -v git`**: This checks whether the `git` command is available on the system. If Git is installed, this command returns the path to the Git binary (e.g., `/usr/bin/git`). If it's not installed, it returns nothing.
- `-v` - In Bash, the `-v` option used with the `command` utility checks whether a command is available in the system (i.e., whether it exists in one of the directories listed in the system's `$PATH` variable).
- **`2>/dev/null`**: Redirects any error output (like "command not found" messages) to `/dev/null`, which effectively hides the error. `2` represents `stderr` (standard error), so this part silences any error message if Git is not found.

### **Exit Code Check:**

```bash
bash
Copy code
if [[ $? -ne 0 ]]; then

```

- **`$?`**: This special variable contains the exit code of the last executed command (`command -v git` in this case).
- **`ne 0`**: This checks if the exit code is **not equal** (`ne`) to 0. In Unix-like systems, an exit code of 0 means the command was successful, and a non-zero exit code means it failed.
    - If `command -v git` returns a non-zero exit code (meaning Git is not installed), the script enters the `if` block.

### **If Git is Not Installed:**

```bash
bash
Copy code
echo "git is not installed. please install git."
exit 1

```

- The script prints a message to the user that Git is not installed and exits with the code `1`. This non-zero exit code signifies that there was an error (Git is missing).

### **If Git is Installed:**

```bash
bash
Copy code
else
    echo "git is installed"
fi

```

- If Git is installed, the exit code of `command -v git` is `0`, so the script moves to the `else` block, printing "git is installed."

# **catching errors as soon as they happen.`set -e`**

In Bash, the `set -e` command is used to modify the behavior of a script so that it **immediately exits** if any command in the script returns a non-zero exit code (i.e., if any command fails).

### **Behavior of `set -e`:**

- When `set -e` is enabled, the script will stop executing as soon as any command fails, instead of continuing to the next line.
- This is useful in preventing a script from continuing when something goes wrong, which can help avoid unintended consequences.

### **Usage:**

```bash
bash
Copy code
#!/bin/bash
set -e  # Enable the -e option

# Commands
mkdir my_directory  # If this fails, the script will exit here
cd my_directory     # This will not run if the above command fails

echo "Script continues if no error occurs"

```

### **Without `set -e`:**

Without `set -e`, the script would continue running even if the `mkdir` or `cd` command failed, which could lead to further issues. For example, running a command in the wrong directory due to a failed `cd` can cause problems.

# **catching un-set variables. `set -u`**

In Bash, the `set -u` option (also called **"nounset"**) modifies the behavior of the script to **treat unset variables as an error** and exit immediately when such an error is encountered.

### **Behavior of `set -u`:**

- When `set -u` is enabled, if you reference a variable that hasn't been defined or initialized, Bash will print an error message and exit the script.
- This is useful for catching bugs where a variable is used before being properly set.

### **Usage Example:**

```bash
bash
Copy code
#!/bin/bash
set -u  # Enable the -u option

echo "This is a test script"
echo "Value of MY_VAR: $MY_VAR"  # MY_VAR is not set, this will trigger an error and exit the script

```

### **Output:**

```arduino
arduino
Copy code
./script.sh: line 5: MY_VAR: unbound variable

```

- In the above example, the script will exit at the line where `$MY_VAR` is used because `MY_VAR` is not defined.

# **showing you each command that runs. `set-x`**

In Bash, the `set -x` option (also known as **"execution tracing"**) enables **debugging** by printing each command (and its expanded arguments) to the terminal before it is executed. This is helpful when you want to see exactly what commands are being run and in what order, especially useful for debugging scripts.

### **Behavior of `set -x`:**

- When `set -x` is enabled, Bash will display each command, along with its expanded arguments, before executing it.
- Each command is prefixed with a `+` sign in the output, indicating that it's part of the execution trace.

### **Usage Example:**

```bash
bash
Copy code
#!/bin/bash
set -x  # Enable execution tracing

echo "Hello, World!"
var="Test"
echo "Variable value: $var"

```

### **Output:**

```bash
bash
Copy code
+ echo 'Hello, World!'
Hello, World!
+ var=Test
+ echo 'Variable value: Test'
Variable value: Test

```

- The `+` sign is used to indicate that the command is being traced.
- You can see each command, including the expanded value of variables.

### **Disabling `set -x`:**

To stop the tracing of commands, you can disable it with `set +x`.

```bash
bash
Copy code
#!/bin/bash
set -x  # Start tracing

echo "Tracing this command"

set +x  # Stop tracing

echo "This command will not be traced"

```

### **When to Use `set -x`:**

- When debugging a Bash script to figure out where something is going wrong.
- To trace the flow of your script and check variable values at each stage.

### **Turning It On/Off Dynamically:**

You can turn on tracing only for specific sections of your script by using `set -x` and `set +x`:

```bash
bash
Copy code
#!/bin/bash

echo "This will not be traced"

set -x  # Turn tracing on
echo "Tracing starts here"
var="Debugging"
echo "Variable value: $var"

set +x  # Turn tracing off
echo "Tracing is now off"

```

# **using all 3 set commands together .`set -eux`**

The `set -eux` command in Bash combines several options to modify script behavior, enhancing debugging and error handling.

### **Combined Behavior (`set -eux`):**

When used together, `set -eux` provides robust error handling and debugging capabilities:

- **Immediate Exit on Error (`e`):** The script will terminate as soon as any command fails.
- **Error on Unset Variables (`u`):** The script will terminate if it encounters an unset variable.
- **Command Tracing (`x`):** Every command and its arguments will be printed before execution, providing visibility into what the script is doing.

### **Example Script with `set -eux`:**

```bash
bash
Copy code
#!/bin/bash
set -eux  # Enable error checking and tracing

echo "Starting script"

# Define a variable
name="Bash User"

# Use an unset variable (will cause the script to exit)
echo "Welcome, $username"  # $username is not set

# This line will not be executed
echo "This line will not be reached"

```

### **Output:**

```bash
bash
Copy code
+ echo 'Starting script'
Starting script
+ name='Bash User'
+ echo 'Welcome, '
+ exit 1

```

- **Command Tracing:** Each command is printed with a `+` prefix, showing what is being executed.
- **Immediate Exit on Error:** The script exits after encountering the unset variable error, preventing further execution.

### **When to Use `set -eux`:**

- **Debugging Complex Scripts:** When you want detailed output of commands and need to ensure that errors do not go unnoticed.
- **Production Scripts:** For robust error handling and to ensure that the script does not run with invalid or unset variables.

Combining these options helps create scripts that are easier to debug and more reliable, especially when working with complex or critical automation tasks.

## Reading Files 

reading files using simple redirection

In Bash, **simple redirection** is a technique used to read files by redirecting the content of the file directly into a command or a script. You can use input redirection (`<`) to pass the content of a file to commands like `while`, `read`, and `cat`.

#!/bin/bash

read_file() {

local file_path=”$1”

while IFS= read -r line; do
      echo "$line"
done < "$file_path"

}

read_file “./log.txt”

The given script defines a **Bash function** called `read_file()` that reads the contents of a file line by line and prints each line to the terminal. Here's a detailed breakdown of each part:

### Explanation:

### 1. **Function Definition:**

```bash
bash
Copy code
read_file() {

```

- This line defines the function `read_file()`. Inside the function, a block of code will be executed when the function is called.

### 2. **Local Variable Declaration:**

```bash
bash
Copy code
local file_path="$1"

```

- **`local file_path="$1"`** declares a local variable named `file_path` and assigns it the value of the first argument passed to the function (i.e., `"$1"`).
- The `local` keyword ensures that the `file_path` variable is scoped locally to the function, meaning it only exists within the `read_file` function and will not affect variables outside of it.

### 3. **`while` Loop:**

```bash
bash
Copy code
while IFS= read -r line; do
    echo "$line"
done < "$file_path"

```

- The **`while` loop** reads the contents of the file line by line.
    - **`IFS=`**: This resets the Internal Field Separator (IFS) to ensure that leading and trailing whitespace is not trimmed from each line.
    - **`read -r line`**: This reads each line of the file into the variable `line`. The `r` option prevents backslashes (`\`) from being interpreted as escape characters.
    - **`echo "$line"`**: This prints the contents of each line to the terminal.
- **`done < "$file_path"`**:
    - This part redirects the file located at `"$file_path"` into the `while` loop. The loop continues reading until the end of the file.

### 4. **Calling the Function:**

```bash
bash
Copy code
read_file “./log.txt”

```

- The function `read_file` is called with `./log.txt` as the argument.
- The file located at `./log.txt` will be passed as the `file_path` argument to the function.
- The `while` loop inside the function will read the file `log.txt` line by line, printing each line to the terminal.


## script

A **script** is a set of instructions written in a programming or scripting language that automates tasks or performs a sequence of operations. Scripts are typically used to automate repetitive tasks, configure systems, process data, or manage software applications.

**./** - is a notation used to specify the current directory. It’s commonly used to run executable files or scripts located in the current directory.


## Shell

**What is the shell?**

A user interface that provides access to the OS services.

takes Linux commands and makes the computer do what we want. allows you to communicate with your OS

**what is bash?**

There are many types of shells, but the most common type is called **bash** (born again shell). think of it as a language.

Each type of shell offers unique features, and are better suited to different tasks.

Shell types?

1. bash shell
2. zsh shell 
3. ksh shell 
4. fish 
5. csh/tcsh shell

**How do you tell which type of shell you're using?**

use the code - **echo $SHELL**

**Zsh shell**

to switch to zsh in the terminal just type zsh and to switch back to bash type bash.

how to make zsh your default shell, use this code - ***chsh -s /bin/zsh***

how to customize your zsh, use this code - `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

![image.png](Bash-Module-image.png)

use this to go through the configuration again for the themes etc. ***source .zshrc***

press **i** to get into insert mode

to save changes press  **:wq!**
















