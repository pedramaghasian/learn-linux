
# Module-1 : Understanding Linux Concepts

# Module-2 : Download and install
# Module-3 : System Access and File system

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
# Module-4 : Fundamentals

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

# Module-5 : Linux System Administration

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

# Module-6 : Shell Scripting

## Linux Kernel

![85](images/85.png)

## Introduction to Shell

![86](images/86.png)

## Types of Linux shells

![87](images/87.png)

## Shell Scripting

![88](images/88.png)

## Basic scripts

```bash
#!/bin/bash

# commands 
pwd
echo
hostname
echo
ls -ltrh

# define variables
fullName = 'pedram aghasian'
echo my name is $fullName
```
## Input/Output of Script

![89](images/89.png)

```bash
#!/bin/bash

a = `hostname`
echo Hell, my hostname is $a
echo
echo What is your name ?
read NAME
echo
echo Hello $NAME
echo
```

## if-then Scripts

![90](images/90.png)

```bash
#!/bin/bash

count = 100
if [ $count -eq 100 ]
then
    echo Count is 100
else
    echo Count is not 100
fi
```

```bash
#!/bin/bash

clear
if [ -e /home/pedram/secrete.txt ]
then
    echo "file secrete.txt is exist"
else
    echo "secrete.txt is not exits"
fi
```
## For Loop Scripts

![91](images/91.png)

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
    echo $i
done
```

## do-while Scripts

![92](images/92.png)

```bash
#!/bin/bash

c = 1
while [ $c -le 5]
do
    echo welcome $c 
    ((c++))
done
```

## Case Statement Scripts

![93](images/93.png)

## check other servers connectivity


## Aliases

![94](images/94.png)

`alias` show all aliases

`unalias <aliasName>` delete an alias

## Shell History

1. show history `history`
2. run commands witch in history  `!<command number> !405`
3. history location `cat /home/pedram/.bash_history`

---------------------------------------------

# Module-7 : Networking, Services, System Updates

## Network Components

![95](images/95.png)

## Network files and Commands

![96](images/96.png)
 
 `netstat -rnv`

 `tcpdump -i <interface>`

 ## NIC Information

![97](images/97.png)

## NIC Bonding

![98](images/98.png)

![99](images/99.png)

## New Network Utilities

![100](images/100.png)

![101](images/101.png)

![102](images/102.png)

## Download Files or Apps

![103](images/103.png)
 
## curl and ping commands

![104](images/104.png)

what if server is up but page is down ?? in this case you should use `curl` command.

you can use `curl -O <url>` instead of `wget` for downloading.

## FTP - File Transfer Protocol

![105](images/105.png)

![106](images/106.png)
 
 **Configure FTP**

![107](images/107.png)

**on Ubuntu**

1. `sudo apt install vsftpd`
2.  `apt list | grep vsftpd`
3.  `sudo service vsftpd status`
4.  `cp /etc/vsftpd.conf /etc/vsrftpd.conf.orig`
5.  `sudo nano /etc/vsftpd.conf`
6.  
```text
listen=NO
 listen ipv6=YES 
anonymous_enable=NO
 local_enable=YES 
write_enable=YES
 local_umask=022
 dirmessage_enable=YES 
use_localtime=YES xferlog_enable=YES
 connect_from_port_20=YES
 chroot_local_user=YES 
secure_chroot_dir=/var/run/vsftpd/empty 
pam_service_name=vsftpd 
rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
 rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
 ssl_enable=NO  
pasv_enable=Yes 
pasv_min_port=10000 
pasv_max_port=10100 
allow_writeable_chroot=YES
```
7. `systemctl enable vsftpd`

**FTP Client Configure**

![108](images/108.png)

**if see this error follow as blew**

500 Illegal PORT command.

go to passive mode in ftp> `pass`

## SCP - Secure Copy Protocol

**SCP use SSH protocol**

![109](images/109.png)

![110](images/110.png)

**configure SCP**

![111](images/111.png)

## rsync - Remote Synchronization

**rsync use SSH protocol**

![112](images/112.png)
![113](images/113.png)

**configure rsync**

![114](images/114.png)

## System Updates and Repository

![115](images/115.png)

## System Upgrade/Patch Management

![116](images/116.png)

## Create Local Repository from cd/dvd

![117](images/117.png)

1. make a directory
2. copy all your content to that directory
3. go to your local repo directory and run `dpkg-scanpackages . /dev/null > Release`
4. give you current directory size `du -sh .`
5. give you system space `df -h`
9. `vim /etc/apt/source.list`
10. add the blew line to that file
```text 
 deb [trusted=yes] file:///opt/debs ./
 ```

 ## Advance Package Management

![118](images/118.png)

`dpkg` and `apt` are both package management tools for Ubuntu and other Debian-based Linux distributions.

`dpkg` (Debian Package Manager) is the low-level tool for installing, removing, and managing Debian packages. It is used to install, remove and manage Debian packages. It works on the package files themselves, and does not have the advanced dependency resolution capabilities of apt.

`apt` (Advanced Packaging Tool) is a higher-level tool that is built on top of `dpkg`. It provides a more user-friendly interface for managing packages, and also includes advanced features such as dependency resolution, package searching, and automatic updates. It is the recommended tool for managing packages on Ubuntu and other Debian-based Linux distributions.

In short, `dpkg` is the underlying package management system for Ubuntu and apt is a user-friendly front-end for managing packages on Ubuntu.


1. **check if a package is installed** 

`dpkg -l | grep package-name`

`apt list --installed package-name` 

2. **remove package**

`sudo apt remove package-name`

`sudo apt autoremove`

`sudo dpkg -r package-name` for deleting packages which installed with `dpkg -i`

3. **check dependency of a package**

`apt-cache showpkg package-name`

`apt show package-name`

4. **install package**

`sudo apt install package-name`

`sudo dpkg -i package-name.deb`

install dependency with this `sudo apt-get install -f` command and then run `sudo dpkg -i .deb`

5. **show configuration of package which installed**

`dpkg -L package-name`

`dpkg-query -L package-name`

`sudo find / -user root -group root -name "*package-name*"`

6. **which package this command belongs to**

`dpkg -S /usr/bin/pwd`

7. **search about a package on the repository**

`apt-cache search package-name`

`apt-cache policy package-name`


## Rollback Updates and Patches

![119](images/119.png)

In short, apt update updates the package list, apt upgrade upgrades the packages.
It is a good practice to run apt update regularly to keep your package list up to date and apt upgrade periodically to keep your system up to date.

`sudo apt-get install example=1.0`

**show apt history**

`apt history`

`cat /var/log/apt/history.log`


7-18