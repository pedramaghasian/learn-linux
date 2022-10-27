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

--------------------------

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
5-17
