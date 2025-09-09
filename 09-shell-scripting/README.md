
# SHELL SCRIPTING #

With the thousands of commands available to the command line user, how can we remember them all? The answer is, we don't. The real power of the computer is its ability to do the work for us. To get it to do that, we use the power of the shell to automate things. We write shell scripts.

## What is Shell Scripting ##

Imagine you're tasked with setting up new workstations and user accounts regularly at your job. Instead of manually creating each folder and user account, a simple shell script serves as your efficient digital helper. By automating the creation of multiple directories and user accounts with just a few lines of code, it saves you considerable time and effort, allowing you to concentrate on more critical aspects of your work.

Shell scripting is the process of writing and executing a series of instructions in a shell to automate tasks. A shell script is essentially a script or program written in a shell language, such as Bash, sh, zsh, or PowerShell ?
A basic shell script that will create multiple folders and create multiple linux users at once would look like this.

```
#!/bin/bash

# Create directories
mkdir Folder1
mkdir Folder2
mkdir Folder3

# Create users
sudo useradd user1
sudo useradd user2
sudo useradd user3
```
## Task ##

1. Create a folder on an ubuntu server and name it shell-scripting
![shell-scripting](./img/1.shell-scripting-directory.png)
2. Using the vim editor, create a file called my_first_shell_script.sh
![vim-my-first-script](./img/2.vim-my-first-scrript.png)
3. Put the shell script code above into the new file
![bash-script](./img/3.bash-script.png)
4. Save the file
5. use cd command to change into the shell-scripting directory
6. Use ls -latr` command to confirm that the file is indeed created.
![shell-scripting-output](./img/4.shell-script-output.png)

Something you should notice about the permissions of the newly created file is this -rw-r--r-- which means;
1. The owner of the file has read (r) and write (w) permissions.
2. Members of the file's group have read (r) permission.
3. Others also have read (r) permission.
However, no one has the execute (x) permission, hence the script cannot be executed.
To execute the script, you would typically do something like this.
```
./my_first_shell_script.sh
```

./This prefix to the file indicates that the command should look for the file in the current directory.
The dot (.) represents the current directory,
and the slash (/) is a directory separator
when you hit enter, you should get a response like
```
bash: ./my_first_shell_script.sh: Permission denied
```
![permission-denied](./img/5.permission-denied.png)

Notice that we now have a Permission denied error which can easily be resolved by giving the file the necessary permission it requires.
But, did you also notice the mention of "bash" at the beginning of the error message? It indicates that the error message is coming from the Bash shell itself. Bash is the command interpreter or shell that you're using in the terminal to execute commands.

1. Add the execute permission for the `owner` to be able to execute the shell script

![execute-permission](./img/6.execute-permission.png)
2. Run the shell script.
![run-shell-script](./img/6.run-shell-script.png)

3. Evaluate and ensure that 3 folders are created

![folders-created](./img/7.folders-created.png)

4. Evaluate and ensure that 3 users are created on the linux server

![users-created](./img/8.users-created.png)

## What Is a Shebang (#!/bin/bash) ? ##
Notice that, at the beginning of the shell script, we have `#!/bin/bash` written there. This is what is called a shebang. It is a special notation used in Unix-like operating systems like Linux, to specify the interpreter that should be used to execute the script. In this case, #!/bin/bash specifically indicates that the Bash shell should be used to interpret and execute the script.

You can explore the /bin folder and see the different programs in there. bash is one of them which is used as the interpreter in that script. If we wanted to use another shell like sh, the shebang would be updated to #!/bin/sh

/bin/bash: This is the absolute path to the Bash shell executable. It tells the system to use the Bash interpreter located at /bin/bash to run the script.
Without a shebang line, the system may not know how to interpret and execute the script, and you may need to explicitly specify the interpreter when running the script.

## Variable Declaration and Initialization: ##
In programming generally, not just shell scripting, variables are essential for creating dynamic and flexible
programs.
Variables can store data of various types such as numbers, strings, and arrays. You can assign values to variables using the operator, and access their values using the variable name preceded by a $ sign.
Lets explore a few examples:
```
Example: Assigning value to a variable:

name="John"
```

From the example above, "John" was asigned to the variable "name".

Now that the variable is assigned, you may ask, how then can i use it?

## Retrieving value from a variable ##
After assigning a value to a variable, as shown in the previous example where we assigned "John" to the variable name, you can utilize this variable in various ways in your script or program. One of the most straightforward methods to use or retrieve the value stored in a variable is by echoing it back to the console. This is done using the `echo` command in shell scripting.
```
echo $name
```
This command instructs the shell to print the value of name to your screen, which, in our case, would output `John`

![variable-declaration](./img/9.variable-declaration.png)

echo is a command used to print a text, variables or values. In this example, echo is used to print a variable which stores a value.