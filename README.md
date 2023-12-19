# Linux-commands

## Permission
``` sudo ```

To provide a temporary grant to users or user groups privileged access to system resources.
so that they can run commands that they cannot run under their regular accounts. If below command show error on permission then add this prefix.

## process
To see the running process

``` ps ```

To list any process listening to the port 8080:

``` lsof -i:8080 ```

To kill any process listen to port 8080:

``` kill $(lsof -t -i:8080) ```

or more violently:

``` kill -9 $(lsof -t -i:8080) ```

``` killall <process name> ``` to kill all the process


## Folders

To list all folder

``` ls ```

To allow you to print the current working directory on your terminal. 

``` pwd ```

To create a folder

``` mkdir ```

To cp and mv commands are equivalent to the copy-paste and cut-paste in Windows. But since Linux doesn’t really have a command for renaming files. we also make use of the mv command to rename files and folders.

``` cp <source> <destination> ```

``` mv <source> <destination ```


To remove file and folder

``` rm <file name> ```
``` rm -r <folder/directory name> ```
``` rm -rf <folder_name> ```

To Create a new file

``` touch <file name> ```

To Open a file in the terminal

``` cat <file name> ```

To echo text on the terminal

``` echo <Text to print on terminal> ```
Note: we can use this to echo some text on file also

## Work on Zip and tar files

tar command in Linux is used to create and extract archived files in Linux. We can extract multiple different archive files using the tar command.
For Compress

``` tar -cvf <archive name> <files seperated by space> ```

For Extract

``` tar -xvf <archive name> ```

To zip and unzip the command

``` zip <archive name> <file names separated by space> ```

``` unzip <archive name> ```


## To compare files

The diff, comm, and cmp commands compare differences 

``` diff <file 1> <file 2> ```

- Say the actual text

``` cmp <file 1> <file 2> ```

- tells the line number, not the actual text

``` comm <file 1> <file2> ```

## server

To connect to an external machine on the network with the use of the SSH protocol

``` ssh username@hostname ```


To use the external OS start and stop the service

``` service ssh start ```

``` service ssh stop ```

``` service ssh start ```

## File permission and File Ownership

#### To view the permission

``` ls -l ```

#### CHMOD file permission

The chmod gives us the functionality to change the file permissions

- change mode of the file
- r, w, x -> read, write, execute

Syntax:
``` chmod [options] [mode] [File_name]  ```

**options**

`-R`	Apply the permission change recursively to all the files and directories within the specified directory.

`-v`	It will display a message for each file that is processed. while indicating the permission change that was made.

`-c`	It works the same as `-v` but in this case, it only displays messages for files whose permission is changed.

`-f`	It helps in avoiding the display of error messages.

`-h`	Change the permissions of symbolic links instead of the files they point to.


and Chown gave us the file ownership

**mode**

Type of mode

**1) symbolic mode**

using Operator

`+`	Add permissions,
`-`	Remove permissions,
`=`	Set the permissions to the specified values

Using Letter

`r`	Read permission,
`w`	Write permission,
`x`	Execute permission

Reference for user

u	Owner,
g	Group,
o	Others,
a	All (owner, groups, others)

example:

Read, write, and execute permissions to the file owner:

``` chmod u+rwx [file_name] ```

Remove write permission for the group and others:

``` chmod go-w [file_name] ```

Read and write for the Owner, and read-only for the group and others:

``` chmod u+rw,go+r [file_name] ```

**2) Octal mode**

In this method, we specify permission using a three-digit number.

The first digit specify the permission for Owner.

Second digit specify the permission for Group.

Third digit specify the permission for Others. The digits


4	Read Permission,
2	Write Permission,
1	Execute Permission

Calculate make permission

example:

``` chmod 674 [file_name] ```

6 represents permission of the file Owner which is (rw).(4+2),
7 represents permission of Group which is (rwx). (4+2+1),
4 represents permission of Other which is (r). (4)

#### CHOWN File Ownership

``` chown [options] new_owner[:new_group] file(s)```

- `chown`: The base command.
- `options`: Optional flags that modify the behavior of the `chown` command.
- `new_owner[:new_group]`: The new owner and optionally the new group. If `new_group` is omitted, only the owner is changed.
- `file(s)`: The file or files for which ownership is to be changed.

**Options available in `chown`**

```-c ```

- utilized to report when a file change is made. 
- when you want to receive notifications about ownership alterations.

ex:

``` chown -c master file1.txt ```

This command notifies you when the ownership of `file1.txt` is changed, providing valuable feedback for tracking modifications.


```-v```
- showing detailed information for every processed file

ex:
chown -v master file1.txt
By using this command, displaying information about each file processed during the ownership change.

``` -f ```

- suppress most error messages and forcefully or silently change ownership, even when not permitted.

ex:
``` chown -f master file1.txt ```

## Networking

To show a List of all network and system IP addresses and other Information.

``` ifconfig ```

To trace out all information of IP Address, the hostname, or the domain name of the endpoint.
By which we can see all the routers that your data pass through to reach the destination.

``` traceroute <destination address> ```

## Downloads

### Wget

Wget is a free utility for downloading files from web. It is a command-line tool that can be used to download files over HTTP, HTTPS, and FTP protocols

##### syntax:
```wget [options] [URL]```

##### example:

To download skype

``` wget https://repo.skype.com/latest/skypeforlinux-64.deb ```

After installing it

```sudo apt install ./skypeforlinux-64.deb```

## package management.

### snap

- a snap is a containerized application that includes all of its dependencies
-  Snaps are a software deployment and package management system that can be installed on various Linux distributions. 

why:
- Install software: Snap is a universal package manager that allows users to install software that might not otherwise be available.
- Automatic updates: Snaps update automatically and roll back gracefully.

To create snap

```
sudo apt update
sudo apt install snapd
```

example to install skype through snap:
```
sudo snap install skype --classic
```

or can install to snap store



### Deb
- A deb is a collection of files managed by the Debian packages management system
# Ref link:

https://www.digitalocean.com/community/tutorials/linux-commands

https://www.geeksforgeeks.org/chmod-command-linux/

https://www.geeksforgeeks.org/chown-command-in-linux-with-examples/
