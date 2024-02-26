# Lab 2: Linux Directory Structure, Linux and Windows File Server, Windows Server Disk and Storage

[Canvas Link](https://canvas.csun.edu/courses/150468/assignments/1855194)

[PDF Download](https://canvas.csun.edu/courses/150468/files/24362831?wrap=1)

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

## Prerequesites

In order to complete this lab, you will need to have pre-configured a Linux and Windows Server VM. 

## Task 1: Explore Linux Commands 

The Lab Assignment on canvas gives step by step instructions for how to complete this task so I won't cover it here.

## Task 2: Bash Shell Programming

TBA

## Task 3: Task 3: Configure File Server Connecting Windows and Linux (Samba)

TBA

## Task 4: Disks and Volumes (Windows Server)

TBA