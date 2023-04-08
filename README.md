[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

# Tech Vault Interview Questions Bank

<p align="center">
  <img width="1000" src="./images/Tech-Vault.png">
</p>


Note: A documentation of carefully curated technical engineering questions by experienced Engineers who have conducted many interviews. These are amongst popular and important engineering questions to test knowledge of candidates in interviews. 

Any questions taken from external references are referenced [below](#references).  

## Table of Contents

- [X] [Vision 🚀](#vision)
- [X] [What is different in this repo compared to others? 🌟](#what-is-different-in-this-repo-compared-to-others)
- [X] [Contributing 🖊️](#contributing)
- [X] [DevOps 🛠](#devops)
    - [Linux 🐧](#small_blue_diamond-linux)
    - [Networking 🌐](#small_blue_diamond-networking)
    - [Git](#small_blue_diamond-git)
    - [AWS 🌩️](#small_blue_diamond-aws)
    - [Azure 🌩️](#small_blue_diamond-azure)
    - [Terraform 🏗️](#small_blue_diamond-terraform)
    - [Docker & K8s 🐳 🎻](#small_blue_diamond-docker--k8s)
    - [Ansible 🔧](#small_blue_diamond-ansible)
    - [CI/CD 🛠️](#small_blue_diamond-cicd)
    - [DevOps methodology, practices, & Agile](#small_blue_diamond-devops-methodology-practices--agile)
- [X] [System Design 🍥](#system-design)
    - [CDN & Caching ⚡](#small_blue_diamond-cdn--caching)
    - [Databases 📊](#small_blue_diamond-databases)
- [X] [Backend & Frontend](#backend--frontend)
    - [Golang](#small_blue_diamond-golang)
    - [Python](#small_blue_diamond-python)
    - [Java](#small_blue_diamond-java)
    - [JavaScript](#small_blue_diamond-javascript-tsnodejs)
- [X] [Data](#data)
    - [Data Modelling & Schemas](#data-modelling-and-schemas)
    - [Data Architect](#data-architect)
    - [Data Engineering](#data-engineering)
    - [SQL](#sql)
    - [ETL & Data Pipelines](#etl-pipelines)
- [X] [Machine Learning 🤖](#machine-learning)
- [X] [Cyber Security & InfoSecurity 🛡️](#cyber-security--info-security)
- [X] [Interpersonal skills](#interpersonal--behavioural-questions)
- [X] [References](#references)

## Vision

- Coming from a non-technical background and without experience can be difficult for many. So I and my team have decided to create this project where all, non-technical and technical tech professionals, can have a place of reference to technical interview questions and interview prep. This is maintained by a lovely community. If you wish to contribute, feel free to do so. Read this for more info >> [How to Contribute](#contributing) 

## What is different in this repo compared to others?

1️⃣ Real questions asked by and of our Engineers (obviously reworded questions)

2️⃣ Scenario-based questions mirroring actual interviews

3️⃣ Up-to-date and relevant topics

4️⃣ Ongoing updates by experienced Engineers in their fields.

## Contributing 🖊️

- To contribute, please read our [Contributing Guidelines](CONTRIBUTING.md). For any fixes, updates or new additions, please make a pull-request (PR). Thank you!

## DevOps 🛠

### :small_blue_diamond: Linux

<details>
<summary>What is Linux and difference between UNIX and Linux?</summary>

Linux is an open-source operating system based on the UNIX architecture. It was created by Linus Torvalds in 1991. UNIX, on the other hand, is a family of operating systems that was developed in the late 1960s at Bell Labs. The main differences between UNIX and Linux are:

- **License:** UNIX is proprietary, while Linux is open-source and free to use.
- **Development:** UNIX is developed by a few organizations (like IBM, Sun Microsystems, and HP), while Linux has a widespread community-driven development process.
- **Portability:** Linux is more portable and can be used on a wide range of hardware, whereas UNIX is limited to specific hardware platforms.
- **User base:** Linux has a broader user base, including personal computers, servers, and embedded systems, while UNIX is primarily used in enterprise environments.
</details>

<details>
<summary>What is the Linux kernel?</summary>

The Linux kernel is the core component of the Linux operating system. It is responsible for managing the system's resources, providing an interface between hardware and software, and facilitating essential tasks such as memory management, process scheduling, and input/output (I/O) operations.

</details>

<details>
<summary>What are inodes in Linux?</summary>

Inodes in Linux are data structures that store important information about files on a file system. Each file or directory in a Linux file system has an associated inode that contains metadata such as the file's size, permissions, ownership, timestamps, and the location of the file's data blocks on the disk.

When you create a file or directory, the file system assigns a unique inode number to it. The inode number serves as an identifier for the file, allowing the file system to access the inode's information and manage the file accordingly.

Here's a summary of what inodes store:

- File type (regular file, directory, symbolic link, etc.)
- File permissions (read, write, execute)
- Ownership (user and group)
- Timestamps (creation, modification, and access times)
- File size
- Number of hard links to the file
- Location of the file's data blocks on the disk

It's important to note that inodes don't store the file's name or the actual file data. The file name is stored in the directory that contains the file, which associates the name with the inode number. The actual file data is stored in separate data blocks on the disk, and the inode points to these blocks.

Inodes play a crucial role in managing files and directories within a Linux file system, providing an efficient way to access and manipulate file metadata.

</details>


<details>
<summary>Explain the Linux boot process</summary>

The Linux boot process consists of several stages that initialize the system and load the operating system. Here's a brief overview of the key steps:

BIOS/UEFI: When the computer is powered on, the BIOS (Basic Input/Output System) or UEFI (Unified Extensible Firmware Interface) performs initial hardware checks and locates the boot device.

Bootloader: The bootloader (e.g., GRUB) loads from the boot device and presents the available operating systems to the user. It then loads the Linux kernel and initial RAM disk (initrd) into memory.

Kernel initialization: The Linux kernel initializes hardware, sets up memory management, starts essential processes, and mounts the initial RAM disk, which contains essential drivers and tools needed during the boot process.

Root file system: The kernel switches the root file system from the initial RAM disk to the actual root partition on the disk, typically identified by its UUID or device name (e.g., /dev/sda1).

Init process: The first user-space process, called init (e.g., Systemd, SysVinit, or Upstart), starts and manages system services and processes during the boot process and the system's runtime.

Runlevel/target: Init process initializes the predefined runlevel (SysVinit) or target (Systemd), which determines the services and processes to run at startup.

Login prompt: Once all services and processes specified in the runlevel/target have started, the system displays a login prompt, indicating that the boot process is complete and the system is ready for use.

</details>

<details>
<summary>What is a zombie process?</summary>

A zombie process, also known as a defunct process, is a process that has completed its execution but still remains in the process table. This happens because the parent process has not yet read the child process's exit status, which is required to clean up the child process's resources and remove its entry from the process table.

Zombie processes don't consume any system resources, except for the process table entry, which includes the process ID (PID) and the exit status. The operating system keeps this information so that the parent process can eventually retrieve the exit status and perform the necessary clean-up.

More info on zombie processes below:

Typically, a well-behaved parent process will use the wait() or waitpid() system call to collect the exit status of its child processes. However, if the parent process doesn't do this, either due to a programming error or because the parent is still running and hasn't reached the point where it collects the exit status, the child process becomes a zombie.

Zombie processes are usually harmless, but if a system accumulates a large number of them, it could exhaust the available PIDs and prevent new processes from being created. To resolve this issue, the parent process should be fixed to correctly handle its child processes' exit status, or if the parent process is unresponsive or terminated, a system reboot might be necessary.

</details>

<details>
<summary>Difference between soft links and hardlinks?</summary>

Soft links and hard links are two types of file links in a Unix-like file system, such as Linux. They serve different purposes and have distinct characteristics:

**Soft Link (Symbolic Link):**

- A soft link is a separate file that points to the target file or directory by storing its path.
- If the target file is deleted, the soft link becomes a "dangling" link, pointing to a nonexistent file.
- Soft links can span across different file systems and partitions.
- Soft links can link to directories as well as files.
- When a soft link is created, the link count of the target file doesn't change.
- Soft links have different inode numbers than their target files.

**Hard Link:**

- A hard link is a direct reference to the data on the disk, sharing the same inode as the target file.
- If the target file is deleted, the hard link still points to the data, and the data remains accessible until all hard links to it are removed.
- Hard links can only be created within the same file system or partition.
- Hard links cannot link to directories, only to files.
- When a hard link is created, the link count of the target file increases by one.
- Hard links have the same inode numbers as their target files.

In summary, a soft link is a more flexible but less reliable type of link that can point to files or directories across file systems, while a hard link is a more robust link that directly references the file's data, but is limited to the same file system and cannot link to directories.

</details>

<details>
<summary>What are namespaces and c-groups?</summary>

Namespaces and cgroups (control groups) are two Linux kernel features that play a crucial role in implementing process isolation and resource management, especially in containerization technologies like Docker.

**Namespaces:**

Namespaces are a feature that provides process isolation by creating separate instances of certain system resources, which can only be accessed by processes within the same namespace. This isolation helps ensure that processes running in one namespace don't interfere with processes in another namespace

There are several types of namespaces, including:

- PID namespace: Isolates process IDs, allowing each namespace to have its own set of PIDs.
- Mount namespace: Isolates the file system mount points, so that each namespace has its own mount tree.
- Network namespace: Isolates network resources, providing each namespace with its own network stack, including interfaces, routes, and firewall rules.
- IPC namespace: Isolates inter-process communication resources, preventing processes in one namespace from communicating with processes in another namespace.
- UTS namespace: Isolates system identifiers like hostname, allowing each namespace to have its own unique hostname.
- User namespace: Isolates user and group ID mappings, enabling each namespace to have its own set of user and group IDs.

**Cgroups (Control Groups):**

Cgroups are a kernel feature that enables the management and limitation of system resources, such as CPU, memory, and I/O, for a group of processes. Cgroups help ensure fair distribution of resources, prevent resource starvation, and enforce limits on resource usage. Some of the key features of cgroups include:

- Resource limiting: Allows setting limits on resource usage for a group of processes, such as maximum CPU usage, memory consumption, and disk I/O bandwidth.
- Prioritization: Enables setting priorities for resource allocation among different cgroups, helping to ensure that critical processes receive sufficient resources.
- Accounting: Collects resource usage statistics for processes in a cgroup, which can be useful for monitoring, profiling, and billing purposes.
- Control: Provides a mechanism to start, stop, or freeze processes in a cgroup, allowing for better management of process groups.

In combination, namespaces and cgroups provide the necessary isolation and resource management capabilities required to build and run containers, enabling multiple containers to coexist on the same host without interfering with each other or consuming excessive resources.

</details>

<details>
<summary>What are symbolic links?</summary>

Symbolic links, also known as soft links or symlinks, are a type of file link in Unix-like file systems, such as Linux. A symbolic link is a special file that points to another file or directory by storing its path. Symbolic links serve as a reference to the target file or directory, allowing users and applications to access the target through the link.

Symbolic links are useful in various scenarios, such as creating shortcuts, linking to files or directories in different locations, or maintaining multiple versions of a file or directory. Some key characteristics of symbolic links are:

Symbolic links can point to files or directories, and they can span across different file systems and partitions.
If the target file or directory is moved or deleted, the symbolic link becomes a "dangling" link, pointing to a nonexistent location.
Symbolic links have different inode numbers than their target files or directories.
When listing files with the ls command, symbolic links are usually indicated by an "l" at the beginning of the file permissions and an arrow (->) pointing to the target file or directory.

To create a symbolic link in Linux, you can use the ln command with the -s option, followed by the target file or directory and the desired symlink name:

```bash
ln -s target_file symlink_name

Example:

ln -s /path/to/original/file.txt link_to_file.txt

This command creates a symbolic link named link_to_file.txt that points to the file located at /path/to/original/file.txt.
```

</details>

<details>
<summary>What are the different types of permissions in Linux?</summary>

In Linux, there are three main types of permissions for files and directories, which determine how users can interact with them. These permissions are classified into categories based on the user's relationship to the file or directory: owner, group, and others (sometimes referred to as "world" or "public"). The three types of permissions are:

Read (r): Read permission allows a user to view the contents of a file or list the contents of a directory. For files, this means the user can open and read the file. For directories, the user can view the names of files and subdirectories within that directory.

Write (w): Write permission allows a user to modify the contents of a file or make changes within a directory. For files, this means the user can edit, append, or delete the file's content. For directories, the user can create, rename, or delete files and subdirectories within that directory. Note that deleting or renaming files within a directory requires write permission on the directory itself, not the individual files.

Execute (x): Execute permission allows a user to run a file as a program or script, or enter and access a directory. For files, this means the user can execute the file if it is a binary executable or script with a proper interpreter (e.g., a shell script or Python script). For directories, the user can change their current working directory to that directory, and access files and subdirectories within it.

These permissions are usually represented using a combination of letters (r, w, x) and dashes (-) for each of the three categories: owner, group, and others. For example, the permission string -rwxr-xr-- indicates:

- The first character - indicates it's a regular file (a d would indicate a directory).
- The owner has read (r), write (w), and execute (x) permissions: rwx.
- The group has read (r) and execute (x) permissions, but not write permission: r-x.
- Others have only read (r) permission: r--.

Alternatively, permissions can also be represented using octal notation (base-8), where read, write, and execute permissions are assigned values of 4, 2, and 1, respectively. The permissions are then represented by a three-digit number, with each digit corresponding to the owner, group, and others. For example, the permission string -rwxr-xr-- can be represented as 754 in octal notation.

</details>

<details>
<summary>What is swap space?</summary>

Swap space is a dedicated area on a storage device (such as a hard drive or SSD) that functions as an extension of a computer's physical memory (RAM). It is used by the operating system to temporarily store data that does not fit into RAM or when the system experiences memory pressure due to high RAM utilization.

When the operating system needs more memory than is physically available, it can move the least recently used or less important data (called pages) from RAM to the swap space. This process is called "paging" or "swapping out." By doing so, it frees up space in RAM for more critical or frequently accessed data. If the swapped-out data is required again, the operating system will move it back into RAM, possibly swapping out other data in the process. This is called "swapping in."

Swap space can be implemented as a dedicated swap partition or a swap file. In Linux, you can manage swap space using commands such as swapon, swapoff, and mkswap. To check the current swap space usage on a Linux system, you can use the free or swapon -s commands.

</details>


<details>
<summary>What is chmod, chown and chgrp in Linux?</summary>

**chmod**
chmod (change mode) is a command used to change the permissions of a file or directory. You can set read, write, and execute permissions for the owner, group, and others. Permissions can be represented in octal notation (numeric) or using symbolic notation (letters).

Example: For example, to give the owner read, write, and execute permissions, the group read and execute permissions, and others only read permission, you would use:
- Using octal notation: `chmod 754 file.txt`
- Using symbolic notation: `chmod u=rwx,g=rx,o=r file.txt`

**chown**

chown (change owner) is a command used to change the ownership of a file or directory. You can specify a new owner and an optional new group for the file or directory.

Example: For example, to change the owner of file.txt to the user john and the group to developers, you would use:

`chown john:developers file.txt`

**chgrp**

chgrp (change group) is a command used to change the group assignment of a file or directory. You can specify a new group for the file or directory.

Example: For example, to change the group of file.txt to the group developers, you would use:

`chgrp developers file.txt`


</details>

<details>
<summary>What are cronjobs?</summary>

Cronjobs, also known as cron jobs or simply cron, are scheduled tasks that run automatically at specified intervals on Unix-like operating systems, such as Linux. The term "cron" comes from the Greek word "chronos," which means "time." Cronjobs are commonly used for automating repetitive tasks, performing system maintenance, running periodic backups, and other similar activities.

Cronjobs are managed by a daemon called "cron," which runs in the background and executes the scheduled tasks. The configuration for cron jobs is stored in a series of files called "crontabs" (short for "cron tables"). Each user on the system can have their own crontab, and there is also a system-wide crontab.

For example, a cron job that runs every day at 3:30 AM would have the following entry in the crontab:

`30 3 * * * /path/to/command arg1 arg2`

To manage cron jobs, you can use the crontab command with various options:

- crontab -l: List the current user's cron jobs.
- crontab -e: Edit the current user's cron jobs using the default text editor.
- crontab -r: Remove the current user's cron jobs.
- crontab -u USER: Perform an operation (list, edit, or remove) on the specified user's cron jobs (requires root privileges).

</details>

Commands (basic & advanced):

<details>
<summary>What does chmod +x FILENAME do?</summary>

The command chmod +x FILENAME is used to add execute permissions to a file in a Linux or Unix-like system. By adding execute permissions, you allow the file to be run as an executable or script, provided it has the appropriate format and interpreter (e.g., a shell script, Python script, or compiled binary). The +x option specifically grants execute permission to the owner, group, and others (all users).

For example, if you have a script named myscript.sh and you want to make it executable, you would run:

`chmod +x myscript.sh`

</details>

<details>
<summary>Which command will show you free/used memory?</summary>

the free command is used to display information about free and used memory. The command provides details on total, used, free, shared, and available memory, as well as swap space usage.

To use the free command, simply type free in the terminal, followed by any desired options. Some common options include:

- -b: Display memory usage in bytes.
- -k: Display memory usage in kilobytes (default).
- -m: Display memory usage in megabytes.
- -g: Display memory usage in gigabytes.
- -h: Display memory usage in a human-readable format, automatically choosing the appropriate unit (e.g., B, K, M, or G).
- -t: Display a line containing the total amount of physical memory and swap space.
- -s N: Continuously display memory usage information, updating every N seconds.

For example, to display memory usage in a human-readable format, you would run:

`free -h`

</details>

<details>
<summary>Which command will show me the current directory I am in?</summary>

`pwd`

</details>

<details>
<summary>How can I terminate an on going process?</summary>

`kill -9 PID`

</details>


<details>
<summary>Write the command that will display all .yaml files including permissions of each file? ()</summary>

find . -type f -name "*.yaml" -exec ls -l {} \;

</details>


<details>
<summary>How can I found the status of a process?</summary>

Content HERE

</details>

<details>
<summary>What is the command to show all open ports?</summary>

Content HERE

</details>


<details>
<summary>How do you find the process ID of a running process in Linux?</summary>

Content HERE

</details>

<details>
<summary>How do you find the dependencies of a package in Linux?</summary>

Content HERE

</details>

Advanced:


<details>
<summary>Does free memory exist on Linux?</summary>

Content HERE

</details>

<details>
<summary>How can I check if a server is down?</summary>

Content HERE

</details>

<details>
<summary>What is inside /proc?</summary>

Content HERE

</details>

<details>
<summary>A process on the system can no longer log files, what can I do?</summary>

Content HERE

</details>

<details>
<summary>What is LILO?</summary>

Content HERE

</details>

<details>
<summary>What are syscalls in Linux and how do they work?</summary>

Content HERE

</details>

<details>
<summary>What is no route to host?</summary>

Content HERE

</details>

<details>
<summary>What is the difference between a hard link and a symbolic link in Linux?</summary>

Content HERE

</details>

Linux Advanced (Scenario based questions):

<details>
<summary>Explain the linux boot process</summary>

Content HERE

</details>

<details>
<summary>A process on the system can no longer log files, how would you debug?</summary>

Content HERE

</details>

<details>
<summary>How can I check if a Linux system is healthy?</summary>

Content HERE

</details>

<details>
<summary>What happens when you type "ls" or "cd" into a terminal? (go deep and talk about what happens behind the scenes - kernel level)</summary>

Content HERE

</details>

<details>
<summary>How can I check if a server is down?</summary>

Content HERE

</details>

<details>
<summary>How are Linux processes killed on a lower level?</summary>

Content HERE

</details>

<details>
<summary>I have accidentally entered `cd/bin` and done `chmod 644 chmod` - how can I fix this?</summary>

Content HERE

</details>

<details>
<summary>How would you troubleshoot a network connectivity issue in Linux?</summary>

Content HERE

</details>

<details>
<summary>How do you troubleshoot a connectivity issue with a remote server in Linux?</summary>

Content HERE

</details>

<details>
<summary>How do you view and edit the system logs in Linux?</summary>

Content HERE

</details>

<details>
<summary>How do you troubleshoot a DNS issue in Linux?</summary>

Content HERE

</details>

### :small_blue_diamond: Networking

<details>
<summary>What is HTTP? How is HTTPS different?</summary>

Content HERE

</details>

<details>
<summary>TCP vs UDP</summary>

Content HERE

</details>

<details>
<summary>What is DNS and how does it work?</summary>

Content HERE

</details>

<details>
<summary>What is TLS?</summary>

Content HERE

</details>

<details>
<summary>What are CIDR ranges?</summary>

Content HERE

</details>

<details>
<summary>What is ingress and egress traffic?</summary>

Content HERE

</details>

<details>
<summary>What is a switch vs a hub?</summary>

Content HERE

</details>

<details>
<summary>What is a switch vs a router?</summary>

Content HERE

</details>

<details>
<summary>What is HTTPS vs Websockets?</summary>

Content HERE

</details>

<details>
<summary>Explain how a 3 way handshake works?</summary>

Content HERE

</details>

<details>
<summary>Stateless vs Stateful firewalls?</summary>

Content HERE

</details>

<details>
<summary>What are VPCs?</summary>

Content HERE

</details>

<details>
<summary>What is subnetting?</summary>

Content HERE

</details>

<details>
<summary>What is DHCP?</summary>

Content HERE

</details>

Advanced + Scenario based questions:

<details>
<summary>When I type google.com into the browser, what actually happens? (go into as much detail as you can)</summary>

Content HERE

</details>

<details>
<summary>I can't reach a website, how can I troubleshoot? (use deep Linux + networking knowledge)</summary>

Content HERE

</details>

<details>
<summary>Can you break down the OSI model and what does it signify?</summary>

Content HERE

</details>

<details>
<summary>How does mTLS work and compare it to TLS?</summary>

Content HERE

</details>

<details>
<summary>Describe the TCP/IP connection process?</summary>

Content HERE

</details>

<details>
<summary>When and why would one use a TCP over UDP?</summary>

Content HERE

</details>

<details>
<summary>Data transfer between 2 hosts is extremely slow. How can you troubleshoot?</summary>

Content HERE

</details>

### :small_blue_diamond: Git

- What is Git?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- Difference between Git and SVN?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is the basic Git workflow?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- Difference between git pull and Git fetch
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is git cherry-pick?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is the HEAD in Git?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- When do I use Git stash?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What does git reset do?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is Git fork? What is difference between git fork, clone and branch?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is difference between `git stash pop` and `git stash apply`?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>

Advanced:
- I need to update my local repos, what commands do I use?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- I need to rollback to a previous commit and I don't need my recent changes, what do I use?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- How can I amend an older commit?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- What is the command to check the difference between two commits?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- When do you use `git rebase` instead of `git merge`?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>
- Do you know how to undo a git rebase?
  <details>
    <summary>Click here to view the answer</summary>
    
    Content HERE
    
  </details>


### :small_blue_diamond: AWS

-----General--------
- What is AWS? 
- What are two services of AWS where you could store secrets?
- What is the relation between the Availability Zone and Region?
- What is auto-scaling?
- What services can help minimise a DDoS attack?
- What is an AMI?
- What are different types of load balancers?

-----Networking-----
- What is a VPC?
- How do Subnets work?
- What network object do you need to allow a server ingress from the internet?
- What are the different type of load balancers in AWS?
- Whate are subnets? and what are CIDRs?
- How can your resources in the VPC get access to the internet?


-----Scenario-based-----
- I want to create a 3 Tier Architecture. Can you explain step by step of how I can go about this?
- In VPC with private and public subnets, database servers should ideally be launched into which subnet?
- What are some security best pracites for EC2s?
- I created a web application with autoscaling. I observed that the traffic on my application is the highest on Wednesdays and Fridays between 9 AM and 7 PM. What would be the best solution for me to handle the scaling?
- You have an application running on your Amazon EC2 instance. You want to reduce the load on your instance as soon as the CPU utilization reaches 100 percent. How will you do that?


-----Others-----
- Name some managed runtimes for Lambda

### :small_blue_diamond: Azure

- What is Azure?
- What are ARM templates in Azure?
- What is Azure CDN?
- How is Azure App Service different from Azure Functions?
- How to define an Environment Variable on Azure using Azure CLI?
- How would you choose between Azure Blob Storage vs. Azure File Service?
- What is difference between Keys and Secrets in Azure Key Vault?
- What’s the difference between Azure SQL Database and Azure SQL Managed Instance?
- When should we use Azure Table Storage over Azure SQL?
- Explain what is the difference between Block Blobs, Append Blobs and Page Blobs in Azure?

Advanced:

- What to use: many small Azure Storage Blob containers vs one really large container with tons of blobs?


### :small_blue_diamond: Terraform

- What is IaC? What is Terraform?
- What is Terraform state
- What are most common Terraform commands?
- What is Terraform backend?
- What are modules in Terraform?
- What is Terragrunt?
- Explain the workflow of the core Terraform?
- Difference between Terraform, AWS CloudFormation and Azure ARM?
- What is the difference between Terraform and Ansible?
- What are provisioners in Terraform?
- How can two people using the Terraform cloud can create two different sets of infrastructure using the same working directory?
- What is a null resource in Terraform?
- Which command is used to perform syntax validation on terraform configuration files?
- How can I format my current directory of Terraform config files in the HCP format?



Advanced:
- I have 3 people in my team who want to work on the same AWS Infrastructure on Terraform as well as same state. What can I do to ensure there are no clashes?
- In a pipeline, where would you store the Terraform state?
- Can I test my terraform modules? If so, how can I test them? Is there a common framework used to Terraform modules?
- How does state file locking work?
- What is Checkov?
- How can I use Terraform in a pipeline?
- How can one export data from one module to another?
- How can you import existing resources under Terraform management?
- Which command can be used to reconcile the Terraform state with the actual real-world infrastructure?

### :small_blue_diamond: Docker & K8s


Container (Docker):
- What is a container and what are its fundamentals?
- What are c-groups and namespaces in Linux?
- What is Docker and how does it work?
- When do I use Docker Compose vs Docker Swarm and K8s?
- What is a Dockerfile used for?
- Can you explain the basic components of a Dockerfile?
    - What is a FROM in a Dockerfile used for?
    - What is a COPY in a Dockerfile used for?
    - What is a ADD in a Dockerfile used for?
    - What is a CMD & ENTRTPOINT in a Dockerfile used for?
- How is a container different from a virtual machine?
- How can I run a container?
- How can I stop and remove a container?
- How can I attach a shell to a terminal of a running container?
- What is a dangling image?
- What is Docker compose and when is it used?
- 

Advanced:
- What is the difference between COPY and ADD commands in a Dockerfile?
- What is the difference between CMD and RUN commands in a Dockerfile?
- What are some best practices to follow when running containers in production?

Container Orchestration (Kubernetes = K8s):

- What is Kubernetes?
- What problems does Kubernetes solve? 
- What is the difference between Docker and K8s?
- What is a Pod and what does it do?
- How can containers within a pod communicate with each other?
- What is a K8s cluster ?
- What are deployments?
- What are stateful sets?
- How do you restrict pod-to-pod communication in a cluster?
- How can I rollback a deployment?
- What are namespaces? 
- What is the role of the kube-apiserver?


Advanced:

- Can you mention some good practices to follow when creating containers?
- Can you explain a simple K8s cluster architecture and the components within it?
- What happens when a master node fails? 
- What happens when a worker node fails?
- What is an Ingress controller?
- How can one build a highly availabe (HA) cluster in K8s?
- What is the role of ETCD in K8s?

### :small_blue_diamond: Ansible

- What is Ansible? 
- How does Ansible work?
- What is Ansible Galaxy?
- What are Ansible handlers?
- What is Ansible Vault?
- What aer Ansible collections?
- How do you get a list of Ansible predefined variables?
- How is Ansible playbook different from ad-hoc commands?
- What is the recommended for securing secret information used within Ansible playbooks?
- What templating language is directly supported within Ansible for creating dynamic playbooks?
- What protocol does Ansible use for communicating with client systems?
- What is an inventory file?


Advanced:

- Can you name some Ansible best practices? 
- How do you handle errors in Ansible?
- How do you test your Ansible roles and tasks?
- What is Molecule and how does it works?

### :small_blue_diamond: CI/CD

- 

### :small_blue_diamond: DevOps methodology, practices,  & Agile

- What is meant by continuous integratons?
- What are the advantages of DevOps?
- Can you describe some branching strategies you have used?
- What is the blue/green deployment pattern?


## System Design

### :small_blue_diamond: CDN & Caching

- What is a CDN and why would I use one?
- What are CDN edge servers?
- How does CDN caching work?
- What is cache invalidation? 
- What are some cache invalidation methods?
- What is a cache Hit?
- What is a cache Miss?
- Can you explain a caching workflow?


----

- What is the CAP Theorem?
- Explain the difference between horizontal scaling and vertical scaling?
- Difference between forward proxy and reverse proxy?
- What is Load Balancing and how does it work? How does it relate to reverse proxies?
- Name me some common load balancers
- What is a microservice architecture and when would I consider using one?


### :small_blue_diamond: Databases

- What is a database?
- What is DBMS (Database Management System)?
- What is the schema referred to in a Database?
- What are different types of databases?
- Advantages & Disadvantages of using relational databases?
- Advantages & Disadvantages of using NoSQL relational databases?
- What is a key-value database? What are some examples of this?
- What are graph databases? Name some examples?
- What is database replication?
- What is master-slave replication? And what is master-master replication?
- What is Synchronous vs Asynchronous replication?
- What are indexes in databases?
- How can one improve query performance by using index hunting?
- What do you understand by ‘Atomicity’ and ‘Aggregation’?
- What is database partitioning?
- 


Advanced:

- What are message queues? And what are message brokers?
- How does the publish-subscribe model work?
- Can you explain how an event-driven architecture works?
- What is an API Gateway? How is this different from load balancers?
- Explain why CDN (in)availability may be a problem for using WebSockets? 

## BackEnd & FrontEnd 


### :small_blue_diamond: Golang

- What is Go?
- Why was the Go langauge created?
- What is a pointer?
- What is the difference between the = and := operator?
- What are goroutines?
- Does Go have exceptions?


Advanced:
- Implement a function that reverses a slice of integers?
- What are generics and how do they work?


### :small_blue_diamond: Python

- 

### :small_blue_diamond: Java

- 

### :small_blue_diamond: JavaScript (TS,nodeJS...)

- What is TypeScript?
- What are the differences between TypeScript and JavaScript?
- Why use TypeScript?
- What are the advantages of TypeScript?
- What are Types in TypeScript?
- What are Type Assertions in TypeScript?
- What are the Primitive data types?
- What are the special data types in TypeScript?
- What are interfaces in TypeScript?
- Interfaces Vs Types?


## Data

### Data Modelling and Schemas: 

- Define data modelling and the benefits of implementing a data model? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Data modeling is the process of creating a visual representation of either a whole information system or parts of it to communicate connections between data. Data modeling concepts create a blueprint for how data is organized and managed in your organization. Data models give developers and non-technical stakeholders a simplified way to have meaningful conversations about the needs of the business and how data insights can fuel better decision making.
    
    </details>


- What are some of the design schemas used when performing data modelling? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: Star Schema. Snowflake Schema. Galaxy Schema.
    
    </details>

- What are the three types of data models? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Entity models, relational and dimensional
    
    </details>

- What is a table (entity) and column (attribute)? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: A row in a database table is an entity. A column header of a database table is an attribute. 
    
    </details>


- What is normalisation/denormalisation and what is its purpose?

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Normalization is the technique of dividing the data into multiple tables to reduce data redundancy and inconsistency and to achieve data integrity. On the other hand, Denormalization is the technique of combining the data into a single table to make data retrieval faster.
    
    </details>


- What are the main relationships which can be found in a data model? (name 3)

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: one to one, one to many and many to many
    
    </details>


- Explain the two different types of design schemas (snowflake and star)? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Snowflake and star are two different types of design schemas used in data warehousing. In a snowflake schema, the data is organized into a hierarchy of tables, with each table having multiple child tables. In a star schema, the data is organized into a central fact table and several dimension tables that connect to it.
    
    </details>


- What is a data mart? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: A data mart is a subset of a larger data warehouse that is designed to serve a specific business function or department. It contains a smaller subset of the data found in the overall data warehouse. 
    
    </details>


- How would you describe granularity? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Granularity refers to the level of detail or specificity of data. It describes how finely the data is divided and recorded.
    
    </details>


- How does data sparcity impact aggregation of data sets/sources? 

    <details>
    <summary>Click here to view answer</summary>
    
    Answer: Data sparcity can impact the aggregation of data sets/sources by making it more difficult to obtain accurate and meaningful results. Sparse data can result in incomplete or inaccurate analyses, as well as a loss of insights and trends.
    
    </details>

- In the context of data modelling, what is the importance of metadata? How would you describe the role of metadata in data modelling? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: Metadata is important in data modelling because it provides additional information about the data being modelled. It helps to document the structure and relationships of the data, as well as its origin, quality, and meaning.
    
    </details>


- What is a DDL script? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: A DDL (Data Definition Language) script is a set of commands used to create, modify, or delete database objects such as tables, indexes, or views.
    
    </details>

- What is a fact and dimension? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: In a data model, a fact is a measurable event or transaction, while a dimension is a descriptive attribute of that event or transaction. For example, in a sales data model, a fact might be the quantity of a product sold, while dimensions could include attributes such as the date of the sale, the customer who made the purchase, or the location where the sale occurred.

    
    </details>

- What is an ERD? Entity relationship diagram?

    <details>
    <summary>Click here to view answer</summary>
    Answer: An ERD (Entity Relationship Diagram) is a visual representation of the relationships between entities (tables) in a database. It shows how the tables are related to each other and the nature of those relationships.

    
    </details>


- What are the differences between foreign and surrogate keys? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: Foreign keys are columns in a table that reference the primary key of another table. Surrogate keys are artificial primary keys that are created specifically for use in a database and have no inherent meaning outside of that context.
    
    </details>

- Desribe cardinality

    <details>
    <summary>Click here to view answer</summary>
    Answer: Cardinality refers to the number of relationships between entities in a data model. It describes how many instances of one entity can be related to another entity. Common cardinalities include one-to-one, one-to-many, and many-to-many.

    
    </details>

### Data Architect

- Please state an example of designing, creating, deploying and managing an end to end data architecture project?

    <details>
    <summary>Click here to view answer</summary>
    Answer: A company wants to implement a customer relationship management (CRM) system. The project would involve designing a data architecture to store customer data, creating the necessary databases and tables, and deploying the system. The data would need to be cleansed, transformed, and loaded into the new system. Ongoing management would involve monitoring the data for quality and making any necessary updates or modifications to the system.
    
    </details>

- What are the fundamental skills required for a data architect? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: Strong knowledge of data modelling and database design
    Expertise in database management systems (DBMS) and database administration
    Experience with data warehousing and business intelligence
    Proficiency in data integration, ETL (extract, transform, load) processes, and data migration
    Familiarity with programming languages and software development methodologies
    Excellent analytical and problem-solving skills
    Strong communication and collaboration abilities
    </details>


- What is a data block and a data file? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: A data block is the smallest unit of data that can be accessed or transferred from a database to memory. A data file is a physical storage unit used to store data in a database.
    </details>
    
- What is data warehousing? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: Data warehousing is the process of collecting, storing, and managing large amounts of data from various sources to support business intelligence and decision-making. It involves organizing the data into a centralized repository or data warehouse, where it can be queried and analyzed using business intelligence tools.
    </details>
   

- What are the main differences between 'a view' and 'a materialised view'? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: A view is a virtual table that is based on a select statement and does not store data. A materialized view, on the other hand, is a physical copy of a view that stores data in a table, making it faster to retrieve.
    </details>
   

- What is a junk dimension?

    <details>
    <summary>Click here to view answer</summary>
    Answer: A junk dimension is a single table that contains several low-cardinality attributes that are not related to any specific dimension. It is used to reduce the number of dimension tables in a data warehouse and simplify the schema design.
    </details>

- Please explain in detail data warehousing architecture

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    The source layer, where data is collected from various sources and stored in staging tables.
    The integration layer, where data is cleansed, transformed, and combined into a single format for loading into the data warehouse.
    The storage layer, where the data is stored in a central repository or data warehouse.
    The access layer, where business intelligence tools and applications can retrieve the data for analysis and reporting.
    </details>
 

- What are the different types of integrity constraints? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Entity integrity: ensures that each row in a table has a unique identifier.
    Referential integrity: ensures that relationships between tables are maintained and that foreign keys reference primary keys.
    Domain integrity: ensures that data values meet specific constraints, such as data type or format requirements.
    User-defined integrity: allows users to define their own constraints based on specific business rules or requirements.
    </details>

- Why do data architects enforce and monitor data compliance standards in data systems? 

   <details>
    <summary>Click here to view answer</summary>
    Answer: Data architects enforce and monitor data compliance standards in data systems to ensure that data is accurate, complete, and secure. This helps to maintain data quality and prevent data breaches or other security risks.
   </details>


- Differentiate between OTLP and OLAP

   <details>
    <summary>Click here to view answer</summary>
    Answer: OLTP (Online Transaction Processing) systems are designed for real-time transactional processing and are typically used for day-to-day business operations. OLAP (Online Analytical Processing) systems are designed for data analysis and reporting and are typically used for business intelligence and decision-making.
    </details>


- How do you design and implement a data warehouse? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Analyze business requirements and identify data sources.
    Develop a conceptual data model and logical data model.
    Design the physical data model and schema.
    Develop ETL processes to extract, transform, and load data into the warehouse.
    Implement the database and BI tools.
    Test and validate the system.
    Deploy and maintain the system.
    </details>

- How do you handle data quality issues? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: To handle data quality issues, data architects can implement data profiling and data cleansing processes. Data profiling involves analyzing the data to identify any issues or inconsistencies, such as missing or duplicate data, incorrect data types, or invalid values. Data cleansing involves correcting these issues and ensuring that the data is accurate and complete.
    </details>

- How do you optimise data models for performance? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Normalize the data to reduce redundancy and improve consistency.
    Denormalize the data to improve query performance and simplify the schema.
    Partition large tables to improve query performance.
    Use appropriate indexing to speed up queries.
    Optimize queries to reduce the amount of data that needs to be processed.
    </details>

- Describe your familiarity with big data technologies such as Hadoop and Spark

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Hadoop is an open-source software framework that is used to store and process big data in a distributed computing environment. It uses a file system called Hadoop Distributed File System (HDFS) to store data across multiple machines and a processing engine called MapReduce to distribute processing tasks across the cluster. Hadoop is particularly useful for handling unstructured and semi-structured data, such as log files, social media data, and sensor data.

    Spark is another open-source software framework that is designed to handle big data processing tasks in real-time. Spark is built on top of Hadoop and provides a more flexible and efficient processing engine than MapReduce. It supports various data processing tasks, including batch processing, stream processing, machine learning, and graph processing. Spark is particularly useful for handling large datasets that require real-time analysis, such as financial trading data, social media data, and sensor data.
    </details>

- How do you go about gathering requirements for a new data project? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Meet with stakeholders to understand their business needs and goals.
    Identify the data sources and types of data that will be needed.
    Develop a data model based on the business requirements.
    Define the data quality and security requirements.
    Determine the performance and scalability requirements.
    Establish a project timeline and budget.
    </details>

- How do you hamdle conflicting priorities when working on multiple projects? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: To handle conflicting priorities when working on multiple projects, data architects can prioritize based on business impact, urgency, and feasibility. Communication with stakeholders and project managers can also help to ensure that expectations are clear and aligned.
    </details>

- Which software and design patterns are you familiar with? 

    <details>
    <summary>Click here to view answer</summary>
    Answer: 
    Relational database management systems (RDBMS) such as Oracle and SQL Server.
    NoSQL databases such as MongoDB and Cassandra.
    Data integration tools such as Informatica and Talend.
    Data visualization and business intelligence tools such as Tableau and Power BI.
    Design patterns such as the star schema and snowflake schema for data warehousing.
    </details>

### Data Engineering

- What made you choose data engineering and what does it mean to you? 
- How would you define data engineering? 
- What are data engineers responsible for? 
- What is the difference between a data architect and a data engineer? 
- What is the difference between structured ,semi structured and unstructured data? 
- Describe differences between a data warehouse and an operational database
- How would you increase the revenue of a business using data analytics and big data? 
- What are the advantages of using skewed tables in hive? 
- Explain the hive data model and its components
- What does COSHH/FSCK mean? 
- Why is using a distributed system important in hadoop? 
- Name the core features of hadoop
- Define hadoop streaming
- What is data locality? 
- What does Context object do in Hadoop and why is it important? 
- Name the three reducer phases in hadoop
- What do args and kwargs commands do? 
- List the differences between tuples and lists
- What are the advantages of working with big data on the cloud? 
- Can you describe what happens when a data block is corrupted? 
- How would you explain file permissions in hadoop? 
- Which process would you follow to add a node to a cluster? 
- Can you list python libraries which can facilitate efficient data processing?
- What challenges came up during your recent project, and how did you overcome these challenges?
- Have you ever transformed unstructured data into structured data? and how did you do it? 
- Can you tell me about NameNode? What happens if NameNode crashes or comes to an end?
- How to achieve security in Hadoop?
- What is FIFO Scheduling? 

### SQL

- How can you deal with duplicate data points in an SQL query?
- List objects that are created via the CREATE statement in SQL
- How would you see the database structure in SQL? 
- How would you search for a specific string in a column? 
- What are the differences between DDL, DML and DCL?
- Difference between SQL and MySQL? 
- How is a RDBMS different to a DBMS? 
- What is a self join? name other join commands
- What is the SELECT statement? 
- What are the CRUD commands? 
- What are UNION, MINUS and INTERSECT commands? 
- List the type of relationships in SQL
- How would you load data into tables using SQL? 
- What is PostgreSQL?
- Explain the character manipulation functions in SQL
- What is the difference between RANK and DENSE_RANK() functions? 
- What are tables and fields? 
- What is a schema in a SQL server? 
- How would you create a table with 4 columns? 
- What is a CASE statment? 
- Summarise differences between SQL and NoSQL
- Difference between NOW() and CURRENT_DATE()
- What is a BLOB and TEXT in MySQL?
- How do you remove duplicate rows in SQL? 
- How do you create a stored in procedure in SQL?
- What is the difference between CHAR, VARCHAR datatypes in SQL? 
- What are constraints in SQL? 
- Differences in DELETE and TRUNCATE statements? 
- What is data integrity? 
- What do you understand by query optimisation? 
- What are entities and relationships? 
- Name some aggregate functions which are commonly used in SQL
- What are the syntax and use of the COALESCE function?
- What is the ACID property in a database?
- What is a “Trigger” in SQL?
- What is a subquery in SQL?
- What is a CLAUSE in SQL?
- What is the need for a MERGE statement?
- How can you fetch common records from two tables?
- What are aggregate and scalar functions?
- What are Views used for?
- What are Local and Global variables?


### ETL & Data Pipelines & more

- How would I go about troubleshooting pipelines?



## Machine Learning

- 


## Cyber Security & Info Security

- 

## Interpersonal & behavioural questions


## References:

- intellipaat.com
- Add more links to any references.

## Charity 
- Since this is a community-based project and it is run by the community - we (the creators) do not gain any personal nor financial gain other than helping the community. Instead, any financial gain would be better suited to a charity. So we wanted to take it upon us to help those in need. We, as a community, have chosen a certified charity to donate to. Here is the link to donate to:
    - To ADD charity donation links here.

## License

This project is licensed under the Apache License. See the [LICENSE](LICENSE) file for more details.
