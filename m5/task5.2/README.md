# Module 5. Linux Essentials

### Hello. In this report, I want to present the sequence of actions that I followed to complete task 5.2 of the Linux Essentials module, as well as the new technologies that I mastered in the process of implementation:

1) /etc/passwd file is a file containing a list of user accounts in text format, while /etc/group is a text file which defines the groups to which users belong under Linux and UNIX operating system. File /etc/passwd contains lines of the following form, separated by colons:
username: pswd: uid: gid: uidcomments: directory: shell
which means: username, password,unique identifier of the user, unique identifier of the group, user home directory etc.
File /etc/group has the following format:
group_name:password:group_id:list
the above mentioned fields contain information about group name, encrypted password of the group, group id and list of users belonging to this group.
Using my laptop with Ubuntu 18 installed, I’ve got acquainted with the structure of /etc/passwd  and /etc/group files, defined main users and groups exists in the system:
![stack Overflow](https://image.prntscr.com/image/cABb3UP-SQKh2v9T7plMHQ.png)
![stack Overflow](https://image.prntscr.com/image/dmvPH2NDTfqptxBw-kxdpA.png)
Some users have "nologin" value at the end of their line. This means that these users cannot log on to the system. These users are also called pseudo-users.
To define pseudo-users, I used combination of cat and grep commands:
![stack Overflow](https://image.prntscr.com/image/heWCHJvBTSOSrq1FKq5lLg.png)

2) UID  is the unique identifier of the user within the system, this number is usually not more than 65535
As for UID ranges:
The system UIDs from 0 to 99 should be statically allocated by the system, and shall not be created by applications. The system UIDs from 100 to 499 should be reserved for dynamic allocation by system administrators and post install scripts using useradd.
0 (root), 1-999 (daemons, pseudo-users, system and reserved users), 1000+ (regular users).
For example, to define UID of my local user, I used a combination of cat and grep commands:
![stack Overflow](https://image.prntscr.com/image/EJN4sSRjQEqpNW2uQQQ6kw.png)
The UID value shows the 3rd field, in ma case it is - 100

3) GID is the unique identifier of the group within the system to which the user belongs. The GID value displays the 4th field of /etc/passwd file, for my local user it is 100:
![stack Overflow](https://image.prntscr.com/image/EJN4sSRjQEqpNW2uQQQ6kw.png)

4) To see which groups Linux user account belongs to, can be used both command ‘groups’ and combination of cat and grep commands to view the output from /etc/group file for the specific user:
![stack Overflow](https://image.prntscr.com/image/3RHpemKqSt2cDQi0A7HWPw.png)

5) To add user to the system, both ‘useradd’ and ‘adduser’ commands can be used. The main difference between them is that useradd is a built-in Linux command that can be found on any Linux system; while adduser is not a standard Linux command, basically, it is a perl script that uses the useradd command in the background.
When using ‘useradd’ command without additional options, the user is being added to the system immediately; while ‘adduser’ is and interactive command, that requires to enter user information:
![stack Overflow](https://image.prntscr.com/image/0SvGhcu_R5enrvkOZZTe3Q.png)
![stack Overflow](https://image.prntscr.com/image/UXmlKuMcRi6rfKWFBFuH8g.png)
Basic parameter required to add new user is username. Also, the user can be created with options, like: comment, directory, expiration date, skel_dir etc:
useradd[-c uidcomment] [-d dir] [-e expire] [-f inactive] [-g gid] [-m [-k skel_dir]] [-s shell]
If no options specified, the main parameters are set be default when adding new user with ‘useradd’. Later, it can be modified if needed.

6) To change the name of existing user, ‘usermod’ command with options can be used:
usermod -l new-name old-name
or
usermod -u UID username (to rename by UID)
E.g.:
![stack Overflow](https://image.prntscr.com/image/csWzZdYITu6qsDrTxFhq-w.png)

7) skell_dir - directory /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created:
![stack Overflow](https://image.prntscr.com/image/Iz8ocu74QB2mqRaSu4CsiQ.png)
“skeleton” directory is defined in /etc/default/useradd file:
![stack Overflow](https://image.prntscr.com/image/WWagp4tmRjm7d3NafPuL_g.png)
This defines default group, default home directory, default expire date, the number of days after a password expires until the account is permanently disabled, defines whether the mail spool should be created or no.

8) To remove user from the system, ‘userdel’ command with options can be used.
Use the -r (--remove) option to force userdel to remove the user’s home directory and mail spool:
![stack Overflow](https://image.prntscr.com/image/nzrJvUhZQCKvRb2ylJXgNA.png)

9) To lock and unlock users in Linux system, ‘passwd’ command with -l and -u keys can be used:
passwd -l username - to lock user
passwd -u username - to unlock user
passwd -S username - to verify the status of a user
Example:
![stack Overflow](https://image.prntscr.com/image/fS46mAYgTMaCI0PYO4LCgQ.png)

10) To delete password for user and provide him with a password-free login for subsequent password change, the commands can be used:
First of all open the sudoers configuration file with sudo visudo or any tex editor, and add the following line to the file, replacing user with your username:
user ALL=(ALL) NOPASSWD:ALL
After that delete password for user by running this commands:
passwd --delete username
or
passwd -d username
To verify the user’ password expiration and aging information, chage command can be  used:
chage -l username
Example:
before deleting password:
![stack Overflow](https://image.prntscr.com/image/UPyPTob2Sx2saKQ-WTICxw.png)
![stack Overflow](https://image.prntscr.com/image/WUEA_-gXRy_lB9KJ97QNGg.png)
after deleting password:
![stack Overflow](https://image.prntscr.com/image/ReubXHKRSOax5GHunm1i7A.png)

11) To display the information about the directory in extended format, we may use the command ‘ls’ with keys, for example:
ls -lah /path/to/folder
keys:
-l - output in long format
-a - display a list of all files and folders, including hidden ones, that start with a dot
-р - display a list of files and information about their sizes.
Example in may case to view the information of ‘akseniya’ user directory:
![stack Overflow](https://image.prntscr.com/image/2taO2RiFQ-Co_9ciuwG4vg.png)
Thus, we may see output with multiple columns:
- permissions of files and folders within mentioned directory
- user
- group
- size of files
- the last modification time

12) Initially, each file had three access parameters. Here they are:
- Read - allows to receive the contents of the file, but not for writing. For a directory, allows to get a list of files and directories located in it;
- Write - allows to write new data to a file or modify existing one, as well as create and modify files and directories;
- Execution - allows to run file as a program.
Each file has three categories of users, for which you can set different combinations of access rights:
- Owner - a set of permissions for the owner of the file, the user who created it or is now set by its owner. Usually the owner has all permissions, read, write and execute.
- Group - any user group that exists in the system and is associated with a file. However, this can only be one group, and it is usually the owner's group, although a different group can be assigned to the file.
- Others - all users other than the owner and users belonging to the group of the file. 

13) To define the relationship between file and user, ‘ls’ command can be used.
For example, let’s view the list of files and it’s information within user ‘akseniya’ directory /home/akseniya:
![stack Overflow](https://image.prntscr.com/image/WUaSSou8TQ_CkwmZ9ZzsIQ.png)
In the example file .bashrc we may see that file has the list of set permissions -rw-r--r--, which means that all the users can read file, owner can additionally modify it. The digital value of file permissions is 644. Also we may see that file belongs to user akseniya and group akseniya, and was modified on 7th of August at 10:48.
![stack Overflow](https://image.prntscr.com/image/E4Tpa3FXQGy-Wd4rILgubA.png)

14) To change the owner of the file or directory, command ‘chown’ can be used.
For example, let’s create some new test html file in home directory of user ‘akseniya’and modify file’s ownership by changing it’s owner to user ‘oksans’:
![stack Overflow](https://image.prntscr.com/image/zAPyOsJOTZyPdjzi-awpXg.png)
To change access mode to the file, ‘chmod’ command is used - permissions can be modified both with symbol and digital values.
For example:
sudo chmod +x test.html - set permission to run file for all users
sudo chmod 777 test.html - the same command, but with digital values:
![stack Overflow](https://image.prntscr.com/image/9f4Ud_X3REic_Dt9f-oeXA.png)

15) Octal notation is a numerical system for modifying the permissions on Linux, Mac and other Unix like file systems. Each octal permission can be represented by 3 or 4 numbers; where each of these numbers is an "octal", meaning they range from 0-7. Each one of the numbers represents permissions that can be set to either a file or directory.
For example, let’s change file permissions and give privileges to all users to read, write and execute the mentioned file:
![stack Overflow](https://image.prntscr.com/image/Wxi2ui-AR3KlOzyQI9Twug.png)
Umask, or the user file-creation mode, is a Linux command that is used to assign the default file permission sets for newly created folders and files.
So, what happens when a user creates new files and directories? The system automatically assigns the following permissions a file if using the touch command:
![stack Overflow](https://image.prntscr.com/image/TCe3xOVpTByegcZtu_rRDw.png)
If we create a directory, it assigns the following permission set to it:
![stack Overflow](https://image.prntscr.com/image/DsKLtOW1R2OCBvJTFyKd2w.png)

16) A Sticky bit is a permission bit that is set on a file or a directory that lets only the owner of the file/directory or the root user to delete or rename the file. No other user is given privileges to delete the file created by some other user.
For example, let’s create test directory in home directory of user ‘akseniya’, few files within this directory, enable sticky bit for directory and remove sticky bit after:
![stack Overflow](https://image.prntscr.com/image/YxdZPjiKSgalJL2BOVdoDA.png)
sudo chmod +t /home/akseniya/test - to enable sticky bit
sudo chmod -t /home/akseniya/test - to remove sticky bit
ls -ld /home/akseniya/test - to define whether sticky bit is enabled or not and view other folder permissions
As for mechanism of identifier substitution, we may substitute user in the system using sudo and so commands.
With sudo, we login to the system as superuser with sudo and su commands.
For example:
![stack Overflow](https://image.prntscr.com/image/rfQeXU6qQt_4NFtynYkhiA.png)
su akseniya - requires to enter user password
sudo su akseniya - does not require to enter user password

17) In  the command script should be present the following attributes:
The sha-bang - the sha-bang ( #!) at the head of a script tells your system that this file is a set of commands to be fed to the command interpreter indicated
Special Characters: comments. Lines beginning with a #; command separator [semicolon]; "dot" character match; “ partial quoting [double quote]; ‘ full quoting [single quote]; escape [backslash] etc
Variables.

### Thank you for attention!
