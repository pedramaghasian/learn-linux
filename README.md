# System Access and File system

## Command Prompt
![1](images/1.png)

## Access To Linux System
![2](images/2.png)

**Access To Linux From Mac**
![3](images/3.png)

## New Network Command (IP)
![4](images/4.png)

`ip a`

`ip addr`

`ifup <internet driver name>` `reboot`

## Linux File System 
![5](images/5.png)
![6](images/6.png)
![7](images/7.png)

## Navigating File System
![8](images/8.png)

## What is Root ?
![9](images/9.png)

## File System Paths
![10](images/10.png)

## Directory Listing Attributes
![11](images/11.png)

## Creating Files And Directories
![12](images/12.png)

## Copy Directories

1. `cp -R <source_folder> <destination_folder>`

## linux File types
![13](images/13.png)

## Find Files And Directories

**two main commands are used to find files/directories**
1. `find`

2. `find . -name "pedram.txt"`

3. `locate`

4. `locate "pedram.txt" ` before `yum install mlocate` and `updatedb`


## Difference Between find and locate
![14](images/14.png)

## Changing Password

1. `passwd <userId>`

## WildCards
![15](images/15.png)
1. `touch abcd{1..9}.txt` create 9 files

2. `rm abcd*`

3. `ls -l abcd*`

4. `rm *.xyz`

5. `ls -l ?bcd*`

6. `ls -l *[cd]*`

## Soft and Hard Links
**Link is just a shortcut**

![16](images/16.png)

**yu cannot create soft or hard link within the same directory with the same name.**

**hard links only work within the same partition**

`ls -ltrhi` i = inode


------------------------------
# Fundamentals

## Linux Command Syntax

![17](images/17.png)

1. `ls -l` -l is **options**

2. `ls -l Downloads` Downloads is **argument**

## File Permissions
![18](images/18.png)
1. **user**`chmod u+rwx <fileName>` 

2. **group**`chmod g+rwx <fileName>` 

3. **others**`chmod o-rwx <fileName>` 

4. **everyone**`chmod a-rwx <fileName>` 

**if a directory does not have execute permission (x) you can not cd to the directory**

## Permission using numeric mode
![19](images/19.png)
![20](images/20.png)

## File Ownership

![21](images/21.png)

1. `chown <username> <fileName>`

2. `chgrp  <username> <fileName>`

## Access Control List (ACL)

![22](images/22.png)
![23](images/23.png)

## Help Commands
1. `whatis command`

2. `command --help`

3. `man command`

## Adding Text to Files (Redirects)

![24](images/24.png)

1. `echo "some text" [>> , >] file.txt`

2. `ls -ltrh > file.txt`


## Input and Output Redirects

![25](images/25.png)

![26](images/26.png)

## Standard Output to a file (tee)

![27](images/27.png)

1. `echo "pedram aghasian is the best" | tee file.txt` 

2. `echo "also is network specialist" | tee -a file.txt`

3. `echo "also is network specialist" | tee file1 file2 file3`

## Pipes 

![28](images/28.png)

1. `ls -ltrh | more`

2. `ls -ltrh | tail -1`

## File Maintenance Commands

![29](images/29.png)

1. `cp file.txt newFile.txt ` create newFile.txt and copy file.txt ino it.
2. `cp file.txt /tmp`
3. `mv file.txt newName.txt` rename a file.
4. `mv file.txt /tmp` cut file.
5. `chgrp root file.txt`
6. `chgown root file.txt`
7. `chown root:root file.txt`

## File Display Commands

![30](images/30.png)

## Filters / Text Processors Commands

![31](images/31.png)

1. ### cut

![32](images/32.png)

2. ### awk

![33](images/33.png)

3. ### grep/egrep

![34](images/34.png)

4. ### sort/uniq

![35](images/35.png)

5. ### wc

![36](images/36.png)

## Compare Files (diff and cmp)

![37](images/37.png)

## Compress and unCompress (tar, gzip, gunzip)

**tar :** tar takes a bunch of files together and put it in one container, just like in windows you have bunch of files and zip them together, so tar file does not compress as much as the actual **gzip** command.

1. `tar cvf <fileName>.tar <path>`
2. extract tar file : `tar xvf file.tar`

**gzip :** is actually compress files

3. compress tar file : `gzip file.tar`
4. upCompress file : `gunzip file.tar.gz` or `gzip -d file.tar.gz`

## Truncate File Size

![38](images/38.png)

 shrink or extend a file : `truncate -s <size bit> filename`

 ## Combining and splitting files

![39](images/39.png)

## Linux vs. Windows Commands

![40](images/40.png)

----------------------------------------

# Linux System Administration

## Linux File Editor

![41](images/41.png)

**vi Editor**

![42](images/42.png)

**Exit from Vi** `shift + z + z`

**Undo** `u`

## Difference Between vi and vim Editor

![43](images/43.png)
![44](images/44.png)
![45](images/45.png)

## sed Command

![46](images/46.png)

1. **replace a word and just show the result**`sed 's/oedram/pedram/g' <fileName>`

2. **replace a word and write to that file**`sed -i 's/oedram/pedram/g' <fileName>`

3. **delete a word**`sed 's/pedram//g' <fileName>`

4. **delete all the line which have specific word** `sed '/pedram/d' <fileName>`

5. **remove empty lines from a file** `sed '/^$/d' <fileName>`

6. **remove first line of the file** `sed '1d' <fileName>`

7. **remove first two line of the file** `sed '1,2d' <fileName>`

8. **replace tabs with space** `sed 's/\t/ /g' <fileName>`

9.  **just show line 12 be bad** `sed -n 12,18p <fileName>`

10. **make empty line after every line** `sed G <fileName>`
    
11. **replace every word except word in line number 8** `sed '8!s/oedram/pedram/g' <fileName>`
    
12. **in vim editor** `:%s/oedram/pedram/g`

## User Account Management (useradd, groupadd, usermod, userdel, groupdel)

![47](images/47.png)

**create user**
1. **create user** `useradd spiderman`
2. **get use id**  `id spiderman`
3. **assign a password** `passwd 123456`

**modify user**
1. **modify a user account** `usermod -G <groupName> <userName>`

**delete user**
1. **delete a use with homeDir** `userdel -r spiderman`
2. **show all groups** `cat /etc/groups` or `grep spederman /etc/group`

**create group**
1. **create a group** `groupadd superheros`
2. **show all groups** `cat /etc/groups`

**delete group**
1. **delete a group** `groupdel superheros`
 
 **cat /etc/passwd**

 **username: password : userId : groupId : description : homeDir : shell**

 **cat /etc/group**

 **groupName: groupPassword: groupId : users are part of this group**

**cat /etc/shadow**
 
**show information about users passwords**

## Password Aging

![48](images/48.png)

![49](images/49.png)


## Switch Users and sudo Access

![50](images/50.png)

**grant root access to the user**

- `/etc/sudoers` : and add the user

```text
root ALL=(ALL)    ALL
pedram ALL=(ALL)    ALL
```

- or add the user to the sudoers group

`usermod -aG wheel pedram`

- then with your username you can run sudoers command : ` sudo pedram`

## Monitor Users

![51](images/51.png)

1. `who` : information about how many people are logged in; when there is height load an the system and you want to see who are logged to the system.
2. `last`: tell you all the details are the users that logged in.
- `last | awk '{print $1}' | sort | uniq`
3. `w` : give you little more information.
4. `finger`
5. `id` or `id username` : get information about yourself.

## Talking To Users

![52](images/52.png)

1. `wall` + message + (ctrl + d) : broadcast a message to all users who loggedIn.
2. `write username` : send message directly to the user.

## Linux Directory Service - Account Authentication

**LDAP is a Protocol NOT Directory service**

![53](images/53.png)

## Difference between AD,LDAP,IDM,WinBIND,OpenLDAP

![54](images/54.png)

## System Utility Commands

![55](images/55.png)

**uptime** 

![56](images/56.png)

**which**

`which <command>`  tell you about command

**bc**

`bc` command line calculator

## Processes and Jobs


**Application or service**

it's like a program that's run into your computer, for example NTP - NFS - rsyslog - Apache.

In Windows, daemons are called services, and behave exactly how daemons were previously described.
They exist and operate independent of a user’s login session, and its status can be observed under the Services tab of Windows Task Manager.

**Script**

script is something that written in a file, and they can be execute.

**Process**

when you run an application it actually generate process with process id.

An instance of a particular executable that is being executed:
For example this could be an .exe program file or a Linux binary. A given application may have several processes running simultaneously.

Typically, an executing program can exist in one of three states:
Running: Active
Sleeping: Inactive
Zombie: A process that has completed execution, but still has an entry in the process table

**Daemon**

is constituently runs in the background.

A process which runs in the background and is not interactive.
They have no controlling terminal on their own from the user’s perspective from the desktop.
They continue to exist and operate regardless of any user being logged into the server if the computer is on.

**Threads**

every process could have multiple threads.

**Job**

a job is something that is created by scheduler like a workorder to run those application and services.

![57](images/57.png)

## ps command

![58](images/58.png)

## top command

![59](images/59.png)
![60](images/60.png)

## kill command

![61](images/61.png)
![62](images/62.png)

## Crontab Command

![63](images/63.png)

## at command

![64](images/64.png)
![65](images/65.png)

## Additional Cron Jobs

![66](images/66.png)

## Process Management

![67](images/67.png)

## System Monitoring

![68](images/68.png)

`netstat -rnv`

## Log Monitoring

![69](images/69.png)

## System Maintenance Commands 

![70](images/70.png)

## changing System Hostname

![71](images/71.png)

## finding System Information

![72](images/72.png)

`cat /etc/os-release`

## System Architecture

![73](images/73.png)

## Terminal Control Keys

![74](images/74.png)

## Terminal Commands 

![75](images/75.png)

watch and save all terminal activity `script activity.lgo`

for exit of `exit`

## Recover Root Password

![76](images/76.png)

## SOS Report

![77](images/77.png)

## Environment Variables

![78](images/78.png)

![79](images/79.png)

## Special Permissions with setuid, setgid and sticky bit

![80](images/80.png)

![81](images/81.png)

1. `which passwd`
2. `ls - l /usr/bin/passwd`
3. with user pedram run`passwd`
4. go to another terminal and `ps -ef | grep passwd`
5. you see this command run by root

![83](images/83.png)
![84](images/84.png)

-------------------------------------------------

# Shell Scripting


6-33
