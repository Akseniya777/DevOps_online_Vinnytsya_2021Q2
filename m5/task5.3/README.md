# Module 5. Linux Essentials

### Hello. In this report, I want to present the sequence of actions that I followed to complete task 5.3 of the Linux Essentials module, as well as the new technologies that I mastered in the process of implementation:

## PART 1

1) In Unix/Linux operating systems, processes can be in one of the following states: RUNNING & RUNNABLE, INTERRRUPTABLE_SLEEP, UNINTERRUPTABLE_SLEEP, STOPPED and ZOMBIE
When the CPU executes a process, it will be in a RUNNING state. When the process is not waiting for any resource and ready to be executed by the CPU, it will be in the RUNNABLE state.
SLEEPING state indicates the process is currently waiting on certain resources (like waiting on I/O, waiting on locks, application code making the process to sleep,…). There are two types of SLEEPING processes:
INTERRUPTABLE_SLEEP: When a process is in INTERRUPTABLE_SLEEP, it will wake up from the middle of sleep and process new signals sent to it.
UNINTERRUPTABLE_SLEEP: When a process is in UNINTERRUPTABLE_SLEEP, it will not wake up from the middle of sleep even though new signals are sent to it.

2) First of I’ve examined pstree command in my Linux terminal (this can be done using man utility or --help key):
![stack Overflow](https://image.prntscr.com/image/Zn4MidJiRfqldses6EiRgw.png)
Pstree is a convenient Linux command used to show running processes in a tree (data structure). If a user name is specified, all process trees rooted at processes owned by that user are shown. Pstree is used as an alternative to the ps command.
Thus, I’ve sorted all the running processes in my system by PID using ‘pstree -np’ command:
![stack Overflow](https://image.prntscr.com/image/iHUncNsPRrCVRrePaDUfiA.png)
![stack Overflow](https://image.prntscr.com/image/ChifzE4zT4CIJcXAzxQRlw.png)
And then listed the chain of current process (chrome in my case) using ‘pstree -s -a 2670’:
![stack Overflow](https://image.prntscr.com/image/etGjOuVcSWyrsyAoz1rMRQ.png)

3) Filesystem /proc is virtual, pseudo file system which provides an interface to kernel data structure. It doesn't contain 'real' files but runtime system information (e.g. system memory, devices mounted, hardware configuration, etc). For this reason it can be regarded as a control and information centre for the kernel. Most of the files in the proc filesystem are read-only, but some files are writable, allowing kernel variables to be changed.
The most distinctive thing about files in this directory is the fact that all of them have a file size of 0, with the exception of kcore, mtrr and self. 

4) Using ‘cat /proc/cpuinfo’ I’ve viewed the information about processor on my laptop (it’s type, model, number of CPU cores, supported technologies etc):
![stack Overflow](https://image.prntscr.com/image/Gufr6ojoTg_B8Cs5t1sMGg.png)
![stack Overflow](https://image.prntscr.com/image/R9mBR-6ZSaSbqJ1eVeY03A.png)

5) To get the detailed information about the running processes in Linux system, ps command with arguments can be used, e.g. both ‘ps -aufx’ or ‘ps -ef’:
![stack Overflow]https://image.prntscr.com/image/kyfVuyolRg6qldgZQJbuRg.png)
![stack Overflow](https://image.prntscr.com/image/dxXMX85UQNmWcelZ4udXUg.png)

6) User-space processes have its own virtual address space.
Kernel processes or threads do not have their own address space, they operate within kernel address space only. And they may be started before the kernel has started any user process (e.g. init).
When managing processes, it is easy to recognize the kernel processes because they have a name that is between square brackets:
![stack Overflow](https://image.prntscr.com/image/x4biylfHTuC_oIVYVe8xxg.png)

7) Using ps command with arguments, we may see the list of processes currently running in the system and their state. For example, I’ve sorted processes by their state using ‘ps aux --sort stat’ command, also we may see the owner of process, whether it is kernel one or user, CPU and RAM resources usage by each process, starting time and commands they are running:
![stack Overflow](https://image.prntscr.com/image/MPgasgsiQpGe4CG4dCM0-w.png)
![stack Overflow](https://image.prntscr.com/image/RenT7MfLQ2yz5brLU5OOWg.png)
Here are the different values that the s, stat and state output specifiers (header "STAT" or "S") will display to describe the state of a process:
               D    uninterruptible sleep (usually IO)
               R    running or runnable (on run queue)
               S    interruptible sleep (waiting for an event to complete)
               T    stopped by job control signal
               t    stopped by debugger during the tracing
               W    paging (not valid since the 2.6.xx kernel)
               X    dead (should never be seen)
               Z    defunct ("zombie") process, terminated but not reaped by its parent
For BSD formats and when the stat keyword is used, additional characters may be displayed:
               <    high-priority (not nice to other users)
               N    low-priority (nice to other users)
               L    has pages locked into memory (for real-time and custom IO)
               s    is a session leader
               l    is multi-threaded (using CLONE_THREAD, like NPTL pthreads do)
               +    is in the foreground process group

8) To display the process of specific user (‘oksans’ in my case) I’ve used ‘ps -U oksans’ and ‘ps aux | grep oksans’ (more detailed information) commands:
![stack Overflow](https://image.prntscr.com/image/Myjo_B8RTYaL22lx8-Edxw.png)
![stack Overflow](https://image.prntscr.com/image/FQw6o4EISwaInzffa3xGCg.png)

9) Except ps utility, the utilities to analyze the existing running tasks in the system, that can be used, are: top and htop.

10) The top command is used to display all the running and active real-time processes in an ordered list and updates it regularly. It displays CPU usage, Memory usage, Swap Memory, Cache Size, Buffer Size, Process PID, User, Commands, and much more.
For example:
![stack Overflow](https://image.prntscr.com/image/I-PmrhnwQ2aqDgvi7jK7qw.png)

11) To display all the processes running by specific user (‘oksans’ in my case), I’ve used ‘top -U oksans’ command:
![stack Overflow](https://image.prntscr.com/image/B0Bu6ACtR1Cw-rytiveRqg.png)
Another option - we may run ‘top’ command without additional keys, then press ‘Shift+U’ keys combination and enter username, which processes we would like to view, then press ‘Enter’.

12) The interactive commands that can be used to control ‘top’ command can be for example:
- ‘Shift+U’ keys combination - to view general statistics of resources usage by certain user;
- ‘Shift +M’ keys combination - to sort statistics of resources usage for all users by memory;
- ‘Shift +P’ keys combination - to sort statistics of resources usage for all users by CPU; 

13) For example, I’ve sorted running processes in Linux system by memory and CPU, using the above mentioned keys combination:
![stack Overflow](https://image.prntscr.com/image/ULUQj_AGQ5O8Wv6_fKYsSQ.png)
![stack Overflow](https://image.prntscr.com/image/87B8qlqzRiyyFvOPcXZi6w.png)

14) To set the priority of certain tasks and then change it’s priority if needed, most often ‘nice’ and ‘renice’ commands can be used with the parameters, to run them we need to detect PID of the needed task. For example:
![stack Overflow](https://image.prntscr.com/image/YufYlD6RTTSSSmHm8MmizA.png)

15) We may also change the priority of running task using ‘top’ command. For this purpose, once given top command, press r. Give PID value of the process you want to change the process value. Give renice value (from -20 to +19):
![stack Overflow](https://image.prntscr.com/image/hr5FM-kGTyagNX3CbuvgbA.png)
![stack Overflow](https://image.prntscr.com/image/RIK30915Q4WljCfktSg55A.png)

16) I’ve examined ‘kill’ command using man utility and --help option:
![stack Overflow](https://image.prntscr.com/image/LK9Su2wwR2KyOH1kzieaEg.png)
Command ‘kill’ is used to send a signal to a process. The most common use is the need to stop a process, which you can do by using the kill command followed by the PID of the process.
Here are the examples of ‘kill’ command examples most common usage:
![stack Overflow](https://image.prntscr.com/image/8C_9grnTS6a7-LGHqKWjJg.png)
![stack Overflow](https://image.prntscr.com/image/xQ_feWw0RLSbDglRnWtI_w.png)

17) Commands jobs, fg, bg are the commands for background process management.
To run the task in the background, we must add the & sign at the end of the command, for example:
![stack Overflow](https://image.prntscr.com/image/iPR70_2mRDyaBQxkiTBURg.png)
To display the list of current background tasks, we can use ‘jobs’ command:
![stack Overflow](https://image.prntscr.com/image/oAbJQI0aTdm0Sr6kjQl5aw.png)
To continue execution of the needed command in the background - the ‘bg’ command can be used.
To take the task out of the background, use the ‘fg’ command

## PART 2

1) Using installed OpenSSH, I’ve connected to Linux server using Windows PowerShell:
![stack Overflow](https://image.prntscr.com/image/z-k1-6n1S4CDC3elb72a9Q.png)
Thus we are able to run the commands on Linux server:
![stack Overflow](https://image.prntscr.com/image/hP40sNh0TReNIYAjmvAC0A.png)
![stack Overflow](https://image.prntscr.com/image/UEfwP1GBTpiWy0Zqz68fnQ.png)
![stack Overflow](https://image.prntscr.com/image/s7sfsBzpQ5K2uK5BdruT0Q.png)
![stack Overflow](https://image.prntscr.com/image/Oy-hg4mzQPO4cgYKa0q_TQ.png")
etc.

2) Basic SSH settings to increase the security of the client-server connection can be the following:
- Strong Usernames and Passwords
- Configure Idle Timeout Interval, e,g:
ClientAliveInterval 360
ClientAliveCountMax 0
- Disable Empty Passwords:
PermitEmptyPasswords no
- Limit Users’ SSH Access, e.g:
AllowUsers user1 user2
- Only Use SSH Protocol 2
SSH has two protocols that it can use. Protocol 1 is older and is less secure. Protocol 2 is what you should be using to harden your security. 
Protocol 2
- Use Another Port
- Use Public/Private Keys for Authentication
For example, I’ve installed Open-SSH server on my Ubuntu virtual machine:
![stack Overflow](https://image.prntscr.com/image/Qf5wIVsXRxmpiVaUkMvQoA.png)
![stack Overflow](https://image.prntscr.com/image/A8tyDE5ETKm1ZlZZPYwVSQ.png)
![stack Overflow](https://image.prntscr.com/image/zgEZw4bgRHaA2IeV4N1Dhg.png)
and by editing SSH configuration file /etc/sshd/sshd_config on my virtual machine, I’ve changed the following settings to increase connection security:
- changed SSH port:
![stack Overflow](https://image.prntscr.com/image/KgYI99f-Tde4iasH80p56Q.png)
- changed Idle Timeout Interval:
![stack Overflow](https://image.prntscr.com/image/cC4POA3yQOa6LHII_c4Qgg.png)
- disabled empty password:
![stack Overflow](https://image.prntscr.com/image/lXaOKxGFQbar78cIf3OKPQ.png)
![stack Overflow](https://image.prntscr.com/image/tNJuXYZFSk26kmXGmuXsVA.png)

3) The list of options for choosing keys for encryption is ssh can be seen using ‘ssh-keygen --help’ command:
![stack Overflow](https://image.prntscr.com/image/z2X0QVAiTCSLi2SRoyQaXg.png)
I’ve generated SSH keys using different options:
![stack Overflow](https://image.prntscr.com/image/K6kQDkEiSQia512aYFaYLQ.png)
![stack Overflow](https://image.prntscr.com/image/NdYXIv_fTu2CnkhaXAFoCg.png)
![stack Overflow](https://image.prntscr.com/image/zUXLbHSwQ0KWmHjMfz6q8g.png)

4) I’ve installed open-ssh server on guest machine and open-ssh client on host machine, tnen enabled port forwarding from guest machine to host machine in network settings:
![stack Overflow](https://image.prntscr.com/image/kyRtiebvRZyL1SYRXsCi0g.png)
![stack Overflow](https://image.prntscr.com/image/OOrCA5DjRNaABurqrLCCuw.png)
Have tested port forwarding on host machine:
![stack Overflow](https://image.prntscr.com/image/7OfQgOqvRC2fb93_gwSkgg.png)

### Thank you for attention!
