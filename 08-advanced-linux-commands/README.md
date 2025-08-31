# Advanced Linux Commands
## File Permissions and Access Rights
In Linux, managing file permissions and ownership is vital for controlling who can access, modify, or execute files and directories. Understanding these concepts allows one to maintain the security and integrity of the system. Below is some key commands and concept related to file permissions and ownership:
## Numeric Representation of Permissions
In Linux, permissions are represented using numeric values.

• no permission = 0  
• read = 4  
• write = 2  
• execute = 1

These values are combined to represent the permissions for each user class. For example:

**Permissions Represented by 7**

• 4(read) + 2(write) + 1(execute) = 7

• Symbolic representation: rwx

• Meaning: Read, write and execute permissions are all granted

• Example Context: A script file that the owner needs to read, modify and execute.

**Permissions Represented by 5**

• 4(read) + 1(execute) = 5 

• Symbolic representation: r-x

• Meaning: Read and execute permissions are granted, but write permission is not

• Example Context:A shared library or a command tool that users can execute and read but not modify.

**Permissions Represented by 6**

• 4(read) + 2(write) = 6 

• Symbolic representation: rw-

• Meaning: Read and write permissions are granted, but execute permission is not

• Example Context:A document or a configuration file that the owner needs to read and modify but not execute.

## Shorthand Representation of Permissions** ##
In addition to the numeric way of showing permissions, Linux also has a shorthand, or symbolic, method for representing file permissions.

**Understanding User Classes from a Permissions Perspective**

Before diving into shorthand permissions, it's important to understand the concept of "user classes" in the context of Linux permissions. Think of user classes as categories of users that Linux recognizes when deciding who can do what with a file. There are three main classes:

• Owner: The person who created the file. Often referred to as 'user'.

• Group: A collection of users who share certain permissions for the file.

• Others: Anyone else who has access to the computer but doesn't fall into the first two categories.

## The Role of Hyphens(-) in Permission Representation ##
In the context of Linux, a hyphen doesn't actually represent a user class. Instead, it's used in the symbolic representation to show the absence of a permission. Practical example below:
```bash
ls -latr
```
![ls -latr](./img/1.ls-latr.png)

**Breakdown of the commands**

• In the output above, you will notice that some of the first character can be a - or d: d means it's a directory, means it's a file.

• The next three characters (rwx) show the permissions for the owner. r stands for read, w for write, and x for execute.
• If a permission is not granted, you'll see a - in its place (eg., r-x means read and execute permissions are granted, but write permission is not).

• The hyphen separates, owner, group, and others

• The following three characters after the owner's permissions represent the group's permissions, using the same r, w, and x notation.

• The last three characters show the permissions for others.
The order the user class is represented is as follow;

• The first hyphen "-" → User  
• The second hyphen "-" → Group  
• The third hyphen "-" → Others  
## File Permission Commands ##
To manage file permissions and ownership, Linux provides several commands:

**chmod command**

The `chmod` command allows you to modify file permissions. You can use both symbolic and numeric representations to assign permissions to the user, group, and others.

For example:

**Created an emply file using the `touch` command**
```
touch script.sh
```
![touch-command](./img/2.touch-command.png)

**Checked the permission of the file with the command below** 
```
ls -latr script.sh
```
![check-permission](./img/3.check-permission.png)

**Updated the permission so that all the user classes will have execution permission**
```
 chmod +x script.sh
```
The above command uses the chmod command with the `+x` option to grant execute permission to the file `script.sh`. The `+x` option adds the execute permission to the existing permissions for all the user classes. 

Now lets check what the file permissions look like

![chmod-command](./img/4.chmod-command.png)

**The same command can be executed to achieve the same result using the numbers approach.**

```
chmod 755 script.sh

```
![number-approach](./img/5.chmod-number-approach.png)

To add execute permissions for all (user, group, others), you would add 1 to each of the three categories, resulting in 755: 

• (4+2+1) = 7 for the user (read, write, and execute), 

• (4+1)=5 for the group (read and execute), 

• (4+1)=5 for others (read and execute). 

Lets consider another example. Imagine the owner of a file is currently the only one with full permissions to `note.txt'. To allow group members and others to read, write, and execute the file, change it to the -rwxrwxrwx permission type, whose numeric value is 777:

```
chmod 777 note.txt
```
**Check the output**
![chmod-number-approach](./img/6.chmod-number-approach.png)

Now, notice the dash ("-") in the first position of the result represents the file type and not a user class. It indicates that the entry is a regular file. 

**chown command**

 The chown command allows you to change the ownership of files, directories, or symbolic links to a specified username or group. 
 
 Here's the basic format:
 ```
 chown [option] owner[:group] file(s)
```
For example, lets assume there is a user on the server called "john", a group on the server called "developers" and you want the owner of `filename.txt` changed from "dare" to "john", and to also ensure that any user in the developer group has ownership of the file as well:
The command would look like below;
```
chown john:developer filename.txt
```
Check the output with `ls -latr`

![chown](./img/6.chown.png)
![chown-result](./img/7.chown-contd.png)

## Superuser Privilledges ##
It is often necessary to become the superuser to perform important tasks in linux, but as we know, we should not stay logged in as the superuser. In most linux distributions, there is a command that can give you temporary access to the superuser's privileges. This program is called sudo (short for super user) and can be used in those cases when you need to be the superuser for a small number of tasks. To use the superuser privilledes, simply type `sudo` before the command you will be invoking

To switch to the root user, simply run
```
sudo -i
```
You can type `exit` to leave the shell

![super-user](./img/8.superuser-command.png)

## User Management on Linux ##
As a DevOps engineer, I will be doing systems administration which involves managing different users on the servers. I need to know how to create a new user, or group, modify their permissions, update password and such similar tasks.

## Creating a User ##
To create a new user on Ubuntu Server, you can use the `adduser` command. Assuming the name of the user to be created is joe. Run the following command:
```
sudo adduser johndoe
```
running this command will prompt you to enter and confirm a password for the new user. You will also be asked to provide some additional information about the user, such as their full name and contact information. Once you provide the necessary details, the user account will be created, and a home directory will be automatically generated for the user.

The home directory represents a file system directory created in the name of the user. Such as `/home/johndoe`. This is where each user created on the server will store their respective data.

![adduser](./img/9.adduser.png)

**Granting Administrative Privileges**

By default, newly created user accounts do not have administrative privileges. To grant administrative access to a user, you can add the user to the sudo group. Users in the sudo group can run commands with administrative privileges. To the johndoe user to the sudo group, run:
```
sudo usermod -aG sudo johndoe
```
![sudo-adduser](./img/10.sudo-grant.png)
•
`usermod:` This is a command that modifies user account properties.

-aG: These are flags used with the usermod command.

•
-a stands for "append" and is used to add the user to the specified group(s) without removing them from other groups they may already belong to.

-G stands for "supplementary groups" and is followed by a comma-separated list of groups. It specifies the groups to which the user should be added or modified.

In the given command, `-aG sudo` is used to add the user `johndoe` to the sudo group.
The sudo group is typically associated with administrative or superuser privileges. By adding `johndoe` to the `sudo` group, the user gains the ability to execute commands with elevated privileges.

**Task:**

- Log out and log back in as the newly created user

![johndoe-login](./img/11.johndoe-login.png)
- Navigate to the `/home/johndoe` directory to explore what has been created. Tip: Use the `cd` command.

![johndoe-home-dir](./img/12.johndoe-home-dir.png)

**Switching User Accounts**

To start using the system as another user, you will need to use the `su` command to switch.

To switch to another user account, use the `su` command followed by the username. For example, to switch to aminat account, run:
```
su aminat
```

You will be prompted to enter the password for the user. Once authenticated, you will switch to the user's environment.

![switch-user](./img/13.switch-user.png)

**Modifying User Accounts**

**Changing User Password**

To change the password for a user, use the `passwd` command followed by the username. For example, to change the password for johndoe, run:
```
sudo passwd johndoe
```
You will be prompted to enter and confirm the new password for the user.

![change-password](./img/14.change-password.png)

- Test the updated password by logging on to the server, using the newly updated password.
![logging-in](./img/11.johndoe-login.png)

**Creating a Group**

To create a new group, use the `groupadd` command. For example, to create a group named "developer," use:
```
sudo groupadd developer
```
![create-group](./img/15.create-group.png)

**Adding Users to the Group**

Use the `usermod` command to add users to the group. For instance, to add users "john" and "jane" to the "developers" group:
```
sudo usermod -aG developers johndoe
```
![add-to-group](./img/16.add-to-group.png)

- The `-aG` options append the "developers" group to the users' existing group memberships.

**Verifying Group Memberships**

To confirm the group memberships for a specific user, use the `id` command. For example, to check the group memberships for the user "johndoe":
```
id johndoe
```
This command displays information about the user "johndoe," including the groups they belong to, such as "developer."
![group-membership](./img/17.group-membership.png)

**Deleting a User**

To delete a user, run the command below
```
sudo userdel username
```
![userdelete](./img/18.userdelete.png)

**Ensuring Proper Group Permissions**

Groups in Linux are often used to manage permissions for files and directories. Ensure that the relevant files or directories have the appropriate group ownership and permissions. For example, to grant the "developers" group ownership of a directory:
```
sudo chown : developers /path/to/directory
```
![chown-group-ownership](./img/19.chown-group-ownership.png)

And to grant read and write permissions to the group:
```
sudo chmod g+rw /path/to/directory
```
![chmod-grant-read-write](./img/20.grant-read-write.png)


## Side Hustle Task 3 ##

- Create a group on the server and name it `devops`

![group-devops](./img/21.group-devops.png)
- Create 5 users `["mary", "mohammed", "ravi", "tunji", "sofia" ]`, and ensure each user belong to the devops group

![users-created](./img/22.users-created.png)
- create a folder for each user in the `/home` directory. For example `/home/mary`

![output](./img/23.output.png)
- Ensure that the group ownership of each created folder belongs to "devops"

![devops-group-ownership](./img/24-devops-group-ownership.png)