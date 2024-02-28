# Lab 2: Linux Directory Structure, Linux and Windows File Server, Windows Server Disk and Storage

[Canvas Link](https://canvas.csun.edu/courses/150468/assignments/1855194)

[PDF Download](https://canvas.csun.edu/courses/150468/files/24362831?wrap=1)

### Table of Contents
[Deliverables](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#deliverables)

[Task 1: Explore Linux Commands](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-1-explore-linux-commands)

[Task 2: Bash Shell Programming](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-2-bash-shell-programming)

[Task 3: Configure File Server Connecting Windows and Linux (Samba)](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-3-configure-file-server-connecting-windows-and-linux-samba)

[Task 4: Disks and Volumes (Windows Server)](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-4-disks-and-volumes-windows-server)

## Deliverables

At the end of this assignment, you will be turning in a word doc containing the following:

**TASK 1** <br>
- The output of the following bash commands:
```bash
echo "A cow is grazing in the summer" > linuxtest3.txt
echo "in the middle of June when all the" >> linuxtest3.txt
echo "other cows are out in the field." >> linuxtest3.txt
cat linuxtest3.txt | sed 's/cow/computer/' > linuxtest4.txt
```

**TASK 1.2** <br>
- The output of the following bash commands:
    - `ls-a>listing`
    - `cat listing | les`

**TASK 1.4** <br>
- The output of the following bash commands:
    - `which chmod`
    - `where is chmod`

**TASK 1.5** <br>
- The permissions of the file working.txt both before and after changing the permissions. 
- An explanation of the following bash commands:
    - `chmod o+w working.txt`
    - `chmod u-r working.txt`
    - `chmod 777 working.txt`

**TASK 1.6** <br>
- Explain the output of the following commands:
    - `dmesg | more`
    - `passwd`
    - `date`
    - `hostname`
    - `arch`
    - `uname -a`
    - `uptime`
    - `whoami`
    - `who`
    - `id`
    - `finger`
    - `wc /etc/passwd`
    - `top`
    - `echo $SHELL`
    - `clear`
    - `history`
    - `head /etc/passwd`
    - `tail /etc/passwd`
    - `more /etc/passwd`
    - `less /etc/passwd`
    - `lost`

**TASK 2** <br>
- Summarize the information in the following directories:
    - /bin
    - /usr/bin
    - /sbin
    - /tmp
    - /boot
- List the devices in /dev
- A screenshot of the contents of the following files (use `cat` to display file contents):
    - /proc/interrupts
    - /proc/devices
    - /proc/cpuinfo
    - /proc/meminfo
    - /proc/uptime
- A screenshot of your login details (use grep)

**TASK 2.1-2.6 & 2.2.1-2.2.2** <br>
- Screenshots of the successful script execution for each task

**TASK 3**
- Screenshot of a successful connection between the Windows Server and Linux VM.

## Prerequesites

In order to complete this lab, you will need to have pre-configured a Linux and Windows Server VM. These instructions are written with the assumption that you have the same Windows Server & Linux machines you used for the last lab. 

## Task 1: Explore Linux Commands 

The Lab Assignment on canvas gives step by step instructions for how to complete this task so I won't cover it here.

## Task 2: Bash Shell Programming

Launch your Linux VM and open the terminal. Run the following commands to create a folder in your home directory and move into it:
```bash
mkdir Lab01
ls #Always verify that the folder was created successfully before moving on
cd Lab01
```

### 2.1 Creating a Bash Script
Once you are in the Lab01 folder, you need to create your first script. First, you want to launch the nano editor by typing `nano hello.sh`. <br>
This will create a file called hello.sh and open the nano editor with that file. Once you have nano open, type the following commands:
```
#!/bin/bash
echo Hello World
```
Save and exit your work by pressing Ctrl+X, then Y, then Enter.

Now that your script is created, you need to launch it. That means first giving the file execute permissions. In the linux terminal, type out the following commands:
```bash
chmod u+x hello.sh
ls -la hello.sh
```
If the command was successful, you should see the output start with `-rwxrw-r-- 1`. That means that the file now can be executed by the owner. 

Run the script by typing `./hello.sh`. You should get an output saying `Hello world`.

### 2.1 Bash Shell Scripting

## Task 3: Configure File Server Connecting Windows and Linux (Samba)

TBA

## Task 4: Disks and Volumes (Windows Server)

*<b>NOTE</b>: These instructions are for using the powershell-only version of Windows Server. If you want to use the GUI-version, the PDF has step-by-step instructions for how to complete it.*

TBA