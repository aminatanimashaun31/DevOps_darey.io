# Linux Fundamentals Mini Project
## Description
This project demonstrates the fundamental steps of Linux administration using AWS EC2 instances. It covers the process of accessing AWS services, managing EC2 instances, and establishing secure connections between local machines and cloud resources. This guide serves as a practical introduction to cloud-based Linux administration.
## Project Steps
## 1. AWS Console Access
The first step involves accessing the AWS Management Console. This is your central hub for managing all AWS services and resources.
![AWS-Console](./img/1.AWS%20console.png)
### Key Points:
* Secure login through AWS Management Console
* Access to all AWS services and resources
* Dashboard provides overview of AWS environment
## 2. EC2 Instance Management
The EC2 (Elastic Compute Cloud) service page allows you to view and manage your virtual servers in the cloud.
![ec2-dashboard](./img/2.EC2-dashboard.png)
### Key Features:
* Overview of all EC2 instances
* Instance status and configuration details
* Resource utilization metrics
## 3. EC2 Instance Operations
Proper instance management is crucial for both cost optimization and security. This section demonstrates how to control your EC2 instances.
![instance-creation](./img/3.ec2-instance.png)

![instance-config](./img/4.ec2-instance.png)

![instance-stop](./img/7.instance-stop.png)
### Best Practices:
* Start instances only when needed
* Stop instances when not in use to optimize costs
* Monitor instance state regularly
* Use appropriate instance types for your workload
## 4. Installed MobaXterm
This section shows the screenshot of the MobaXterm installed on my local machine.
![mobaxterm-installed](./img/MobaXterm-installed.png)
### Key Features:
* Secure SSH connections
* File transfer capabilities
* Terminal emulation
* Multi-platform support
5. ## Getting the public IP address of the EC2 instance
This section shows the screenshot of the public IP address of the EC2 instance.
![public-ip](./img/8.publicip-address.png)

6. ## Connecting to the EC2 instance
This section shows the screenshot of the connection to the EC2 instance. Using the command below to connect to the EC2 instance
```bash
ssh -i "MyNewKeyPair.pem" ubuntu@ec2-13-218-192-192.compute-1.amazonaws.com
```
![ec2-connection](./img/6.ec2-instance-connected.png)
### Key Features:
* Connection to the EC2 instance
* SSH connection
* File transfer capabilities
7. ## Updating the package list
This section shows the screenshot of the package list. Using the command below to update the package list
```bash
sudo apt update
```
![update-package-list](./img/9.update-package-list.png)
### Key Features:
* Updating the package list
8. ## Installing tree command
This section shows the screenshot of the tree command. Using the command below to install the tree command
```bash
sudo apt install tree
```
![tree-install](./img/10.tree-install.png)
### Key Features:
* Installing the tree command
9. ## Using tree command
This section shows the screenshot of the tree command. Using the command below to use the tree command
```bash
tree / -L 1
tree / Documents
tree / Downloads
```
![tree-usage](./img/11.tree-command-usage.png)

10. ## Upgrading the package
This section shows the screenshot of updating the package. Using the command below to upgrade the package
```bash
sudo apt upgrade
```
![update-package](./img/12.update-installed-package.png)

11. ## Removing tree command
This section shows the screenshot of removing the tree command.
```bash
sudo apt remove tree
```
![remove-tree](./img/13.remove-tree.png)

12. ## Installing Nginx
This section shows the screenshot of the installation of Nginx. Using the command below to install Nginx
```bash
sudo apt install nginx
```
![nginx-install](./img/14.install-nginx.png)