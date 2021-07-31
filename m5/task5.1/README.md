# Module 5. Linux Essentials

### I’ve performed my laboratory work using EC2 instance from AWS platform with Centos 7 OS installed:
![stack Overflow](https://image.prntscr.com/image/hQdVBJ_gT4SiKJnMhC514w.png )

## PART 1

* first of all I’ve logged in into the server both as centos user, and opened the second session under root user, after that I’ve determined the users registered in the system, as well as what commands they execute, using commands w, whoami and finger (to use finger I had to install it on Centos server first of all: sudo yum install finger):
![stack Overflow](https://image.prntscr.com/image/0vhcnh7kR9OTsCLVQEHuGQ.png )
![stack Overflow](https://image.prntscr.com/image/-f5Pu34eTIKYQMofSFvnrw.png)
![stack Overflow](https://image.prntscr.com/image/wVu89nXGSAumFJ0fJkC46Q.png)

* secondly, I’ve changed server root password using passwd command and examined basic parameters of passwd with man:
![stack Overflow](https://image.prntscr.com/image/-TZU03omTV6zKc0OLab_yw.png)
![stack Overflow](https://image.prntscr.com/image/cONeqUjqRySoeiVy0kcevQ.png)
when updating user password, the system file /etc/passwd is changed:
![stack Overflow](https://image.prntscr.com/image/1SDVA8d7Q-uefNUkJ00P-w.png)

* then I’ve changed my personal information using chfn command, after making changes viewed personal info using finger command; as we as have described in  .home and .project files (created them first) in user home directory that I’m working on laboratory work. The mentioned commands output:
![stack Overflow](https://image.prntscr.com/image/goIV6EQkRA6PXkDzqoUwaw.png)
![stack Overflow](https://image.prntscr.com/image/09oB-NZxQlSMc5hyroLSLQ.png)

* I’ve got acquainted with the Linux help system using main command, viewed the information about previously discussed commands (shfn, passwd, finger):
![stack Overflow](https://image.prntscr.com/image/p-6nUsGmQkWdJrTu7i9E7w.png)
![stack Overflow](https://image.prntscr.com/image/9dALtZ0mTy6EYxXVhuyyNQ.png)
![stack Overflow](https://image.prntscr.com/image/ZcT7ed7dRkKWiToBKYQztg.png)
For example, the main keys I used:
finger centos -l - to view personal info of user ‘centos’
sudo chfn centos - to update personal info of user ‘centos’
sudo password - to update the password of user ‘root’
sudo password centos - to update the password of user ‘centos’

* I’ve explored the more and less commands usage using Linux help system (man), as well as viewed the content of bashrc file using these commands:
![stack Overflow](https://image.prntscr.com/image/1CZAYYQtSI2Mgk_2MHAjIQ.png)
![stack Overflow](https://image.prntscr.com/image/HoIBzySQRUGhlwQSKELUXw.png)
![stack Overflow](https://image.prntscr.com/image/y7ezvwE5TaCoMofWOyzcpw.png)
![stack Overflow](https://image.prntscr.com/image/jDxzc8UlTLq7VlISJxR6CQ.png)

* using ls command, I was able to list the content of home directory (-la keys - to view hidden files and directories also):
![stack Overflow](https://image.prntscr.com/image/AqxdDdsOSZmMxXRgAHv5eA.png)

## PART 2

* first of all I’ve installed tree command on Centos (sudo yum install tree) in order to use it further, and examined it using man utility:
![stack Overflow](https://image.prntscr.com/image/JC8B0xoFQVKqo32ud2X6Uw.png)
![stack Overflow](https://image.prntscr.com/image/qnw-8QD1Qc_5QgGma824-w.png)

* I’ve viewed list subdirectories of /var/log directory using tree command:
![stack Overflow](https://image.prntscr.com/image/IfJUxFuCSbeDszfJJ5Cg2w.png)

* I’ve searched for all files that contain a character ‘c’ within certain directory using grep -lR "c" ./ command:
![stack Overflow](https://image.prntscr.com/image/O5eEi9WQSoijgZ5KqaAvGg.png)

* to determine type of file, command file can be used:
![stack Overflow](https://image.prntscr.com/image/sWOdjqHPTzSjPXIgc_zyjg.png)

* I’ve mastered my skills of navigating the file system using relative and absolute paths
![stack Overflow](https://image.prntscr.com/image/npZo4fnwQI_nZU3XfJ-Q9w.png)
To navigate to the home directory from everywhere, “cd" or "cd ~" can be used.

* using ls command, we may list the contents of the directory or directories. ls -la keys are used to display all the files and folder within certain directory, including hidden files and directories (with . at the beginning):
![stack Overflow](https://image.prntscr.com/image/dwNMuFFSS-2SXMiS3bEfxw.png)

* the next action I’ve performed - have created a subdirectory in the home directory and in this subdirectory created a file containing information about directories located in the root directory; after that I’ve viewed the created file. Commands mkdir, tree, less were used:
![stack Overflow](https://image.prntscr.com/image/cj5y6w9mQFO293ltmG4khw.png)
![stack Overflow](https://image.prntscr.com/image/tUaUKm9RTwyWdOlW_xqo6Q.png)

* I’ve copied created file with output of tree command into my home directory using relative and absolute addressing; then deleted previously created subdirectory and file copied to home directory:
![stack Overflow](https://image.prntscr.com/image/I-jGsHj7THWGhwjMC7z1nQ.png)
![stack Overflow](https://image.prntscr.com/image/pAkB-NQNR0ubeScebr3VXg.png)

* I’ve created a subdirectory test in the home directory, copied the .bash_history file to this directory and changed its name to labwork2:
![stack Overflow](https://image.prntscr.com/image/IAozx2gHQlq4yc6zjyQOow.png)

* I’ve created a hard and soft link to the labwork2 file in the test subdirectory. To determine whether hard or soft link is, ls -l command can be used:
![stack Overflow](https://image.prntscr.com/image/G94B7QYVSMmuL6lM-I6aTw.png)
![stack Overflow](https://image.prntscr.com/image/rfAOwh6dRmKSvc9j8dOkxQ.png)

* I’ve changed the data by opening symlink using vi text editor - when opening  symlink, the file labwork2 was opened automatically. So after making some changes, we may see that modification time of the file labwork2 has been changed:
![stack Overflow](https://image.prntscr.com/image/ziF8ZHAfQEyedQmBKT2ieg.png)

* then I’ve renamed hard and soft links using mv command:
![stack Overflow](https://image.prntscr.com/image/p-GoUzEmTOOX3nFR4__xKA.png)

* finally have deleted labwork2 file: symlink has stopped to work, while hard link still displays the content of deleted file:
![stack Overflow](https://image.prntscr.com/image/-mlDNAoLSD2i0Qm5w6sSjg.png)

* I’ve found all files that contain the squid and traceroute sequence using locate command:
![stack Overflow](https://image.prntscr.com/image/COpDa-IeQcebMa8mm86aJg.png)

* using fdisk -l and df -f commands I’ve determined partitions mounted in the system, as well as the types of these partitions.:
![stack Overflow](https://image.prntscr.com/image/8VWwDch4QPK7MAxcQS64TA.png)

* using sequences of grep, less and wc -l commands, I’ve counted the number of lines containing specific text in certain file:
![stack Overflow](https://image.prntscr.com/image/Jol7bxICTdaN9e-8fjar9g.png)

* then using find command, I’ve found all the files in /etc directory containing the ‘host’ character:
![stack Overflow](https://image.prntscr.com/image/52s8a4JnSaGLoZJjsKK1Ng.png )
to find the list of files:
find '/etc' -name '*.*' -exec grep 'host' {} /dev/null \;
to save command output as text file:
find '/etc' -name '*.*' -exec grep 'host' {} /dev/null \; > find_host.txt

* using grep command with keys (grep -rnw '/etc' -e 'ss'), I’ve listed all objects in /etc directory that contain the ss character:
![stack Overflow](https://image.prntscr.com/image/_E6k0InoS32EDIiclO7Qbw.png)

* I’ve organized print of the contents of /etc directory using ls, dir and tree commands and saved out as text file; viewed the content of saved file using cat command:
![stack Overflow](https://image.prntscr.com/image/_zdC24GoTVW11DrP7BuhHg.png)
![stack Overflow](https://image.prntscr.com/image/KEC9PyphT5yyMWoDTvLtQg.png)
![stack Overflow](https://image.prntscr.com/image/7f9C-PlUSNubM6Kfe5JD4A.png)

* to determine the type of device, mount command can be used: 
![stack Overflow](https://image.prntscr.com/image/k3XcnUcYTGqIfxst1U2FlQ.png)

* to determine the type of file in the system, ‘df -Th’, ‘lsblk -f’ commands can be used for example:
![stack Overflow](https://image.prntscr.com/image/mL0P8qojQS2kf7pFUt0GOQ.png)

* to list the first 5 directory files that were recently accessed in the /etc directory, I used ‘ls -1t /etc | tail -5’ and ‘ls -lht /etc | head -6’ commands:
![stack Overflow](https://image.prntscr.com/image/xFDoWCyZRSi4xD6ILiUufw.png)
![stack Overflow](https://image.prntscr.com/image/5G-4ayA4TIGGKSXX_Yl6Gg.png)

### Thank you for attention!
