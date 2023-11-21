# Linux-commands

## Permission
``` sudo ```

To provide a temporary grant to users or user groups privileged access to system resources.
so that they can run commands that they cannot run under their regular accounts.

## process
To list any process listening to the port 8080:

``` lsof -i:8080 ```

To kill any process listen to port 8080:

``` kill $(lsof -t -i:8080) ```

or more violently:

``` kill -9 $(lsof -t -i:8080) ```

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
 
