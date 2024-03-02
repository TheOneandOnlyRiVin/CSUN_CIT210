# Lab 2: Linux Directory Structure, Linux and Windows File Server, Windows Server Disk and Storage

[Canvas Link](https://canvas.csun.edu/courses/150468/assignments/1855194)

[PDF Download](https://canvas.csun.edu/courses/150468/files/24362831?wrap=1)

### *<b>Disclaimer</b>: For ease of understanding, I've changed Task 2 in the PDF to 2.1.*

### Table of Contents
[Deliverables](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#deliverables)

[Task 1: Explore Linux Commands](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-1-explore-linux-commands)

[Task 2.1: Bash Shell Programming](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-21-bash-shell-programming)

[Task 2.2: Troubleshooting Bash Scripts](https://github.com/TheOneandOnlyRiVin/CSUN_CIT210/blob/main/Lab%20Assigments/Lab%20Assignment%202.md#task-22-troubleshooting-bash-scripts)

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

**TASK 2.1.1-2.1.6 & 2.2.1-2.2.2** <br>
- Screenshots of the successful script execution for each task

**TASK 3**
- Screenshot of a successful connection between the Windows Server and Linux VM.

**TASK 4**
- TBA

## Prerequesites

In order to complete this lab, you will need to have pre-configured a Linux and Windows Server VM. These instructions are written with the assumption that you have the same Windows Server & Linux machines you used for the last lab. 

## Task 1: Explore Linux Commands 

The Lab Assignment on canvas gives step by step instructions for how to complete this task so I won't cover it here.

## Task 2.1: Bash Shell Programming

Launch your Linux VM and open the terminal. Run the following commands to create a folder in your home directory and move into it:
```bash
mkdir Lab01
ls #Always verify that the folder was created successfully before moving on
cd Lab01
```

### 2.1.1 Creating a Bash Script

Once you are in the Lab01 folder, you need to create your first script. First, you want to launch the nano editor by typing `nano hello.sh`. <br>
This will create a file called hello.sh and open the nano editor with that file. Once you have nano open, type the following commands:
```bash
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

### 2.1.2 Creating a Simple Addition Script

For this task, we will be creating a simple bash script that can add two numbers together.

Open nano again, this time creating a file called `calc.sh`. This time, put the following code inside:
```bash
#!/bin/bash
#a simple script
echo "$1 + $2 = $(($1 + $2))"
```
Save and exit from nano, give the file execute permissions, and launch it. You should get an error. That's because this script requires inputs. Try it again using the following command:
```bash
./calc.sh 2 2
```
You should get the following output:
```
2 + 2 = 4
```
When you are scripting with bash, you can push inputs to the function by putting them after the file name and definging them in the script by using `$`. Bash is an interpretive langauge, so it will read them automatically as strings, but depending on the context it will automatically convert them to numbers or other data types as needed.

Feel free to test the code with other numbers to see it's limits.

### 2.1.3 Creating a File Creation Script

In this exercise you are going to be creating a script that creates a file that is specified at runtime. We are going to do this using the `touch` command, which creates a file in Linux.

Open nano through the Linux Terminal again, this time creating a file called `myshell.sh`. Put the following code in the file:
```bash
#!/bin/bash
touch $1
ls > $1
```
Save and exit nano, give the file execute permissions, and then run it/verify the output using the following commands:
```bash
./myshell.sh testfile
ls
```
Make sure testfile is shows up in the file list and then check the contents of the file using `cat`. You should see the following output:
```
calc.sh
hello.sh
myshell.sh
testfile
```
Test the script again, this time creating a file called `testfile1`.

### 2.1.4 Creating a Date File Script

In this exercise you are going to be creating a file whose name will be today's date in the format of ddmmyy.dat.

Open nano again, creating a file called `date.sh`. Put the following code into the file:
```bash
#!/bin/bash
touch `date +%d%b%y`.dat
FILENAME=`date +%d%b%y`.dat
touch $FILENAME
```

In this script, it is actually creating the file twice, using two seperate ways. In the first one, it is directly creating a file using touch and naming it by pulling the day(`%d`), month(`%b`), and year(`%y`) and combining them into a name. In the second, it is creating a variable called `FILENAME` that is contains a string that was created by pulling the day(`%d`), month(`%b`), and year(`%y`) and combining them. It them creates a file and names it using the string in FILENAME.

Save and exit from Nano, then run the script. Check the directory to make sure the file is created.

## Task 2.1.5: Adding Output & Reading Additional Inputs

In this exercise, you will be creating a file like you did in 2.1.3, but this time you will be adding two additional features. The first will be adding the ability to ask the user to input additional variables, and the second will be to echo back when the file is successfully created.

Open nano yet again, creating a file called `creafile.sh`. Input the following code:
```bash
#!/bin/bash
echo 'enter a file name:'
read FILENAME
touch $FILENAME
echo "$FILENAME has been created"
```

In this script, it is asking the user to add an additional input, then using the `read` command to create a variable called `FILENAME` containing a string with the additional input. Then it creates a file using said string and echos back to the command line that it has been created.

Save and exit from Nano. Run the script and make sure to double check that the script successfully created the file.

## Task 2.2: Troubleshooting Bash Scripts

TBA

## Task 3: Configure File Server Connecting Windows and Linux (Samba)

TBA

## Task 4: Disks and Volumes (Windows Server)

*<b>NOTE</b>: These instructions are for using the powershell-only version of Windows Server. If you want to use the GUI-version, the PDF has step-by-step instructions for how to complete it.*

TBA