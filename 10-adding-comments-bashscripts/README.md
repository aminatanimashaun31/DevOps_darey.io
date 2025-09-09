# Adding Comments in Bash Scripts #
Comments are essential in programming, serving as notes to the programmer and anyone else who might read the code.

They explain what the script or parts of the script do, making the code easier to understand and maintain. 
This section will guide you on how to add comments in Bash scripts.

## What Are Comments? ##
Comments are lines in your code that are ignored by the interpreter. In Bash scripts, comments help document the purpose and logic of your code, making it easier for others (and yourself) to follow and understand the script's functionality.
## Single-Line Comments ##
Single-line comments in Bash start with the # symbol. Anything following this symbol on the same line is treated as a comment and is not executed.
```
# This is a single-line comment in Bash
echo "Hello, you are learning Bash Scripting on DAREY.IO!" # This is also a comment, following a command
```
![single-line-comment](./img/1.single-line-comment.png)
## Using Multiple Single-Line Comments: ##
```
# This is another way to create
# a multi-line comment. Each line
# is prefixed with a # symbol.
echo "Here is an actual code that gets executed"
```
![multiple-single-line-comment](./img/2.multiple-single-line-comment.png)
This approach is straightforward and is commonly used for adding brief descriptions or notes spanning multiple lines. 

## Multi-Line Separator-Style Comment ##
* Here’s a complete functional Bash script
```
#!/bin/bash

# --------------------------------------
# Multi-line comment:
# This script will:
# 1. Print a welcome message
# 2. Create a new folder called TestFolder
# 3. List all files in the current directory
# 4. Display a goodbye message
# --------------------------------------

# Print welcome message
echo "Welcome! Let's create a folder and list files."

# Create a new directory called TestFolder
mkdir TestFolder

# List all files in the current directory
ls -la

# Print goodbye message
echo "Goodbye! Script execution completed."
```
## Running the Script ##

* Make the script executable:
```
chmod u+x script.sh
```
* Run the script:
```
./script.sh
```
![script](./img/3.script.png)

![output](./img/4.output.png)
![output-contd](./img/5.output-contd.png)
## Best Practices for Commenting: ##
* Clarity: Write clear and concise comments that explain the "why" behind the code, not just the "what". 
* Maintainability: Keep comments updated as you modify the code to ensure they remain relevant and helpful. 
* Usefulness: Comment on complex or non-obvious parts of the script to provide insights into your thought process and decision-making. 
* Avoid Overcommenting: Don't comment on every line of code, especially if the code is self-explanatory. Focus on parts that benefit from additional explanation.
