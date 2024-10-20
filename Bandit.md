# Bandit
## Level 0
I had to log into the game using SSH. I ran the command `ssh bandit0@bandit.labs.overthewire.org -p 2220` where bandit0 is the username, bandit.labs.overthewire.org is the host (remote server or machine) to which I needed to connect to and 2220 is the port. I entered the password bandit0 and the connection was established.
## Level 0 → Level 1
password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
## Level 1 → Level 2
After logging in I used the command `cat ./-` to get the password from the file '-'. Since '-' can be misinterpreted as an option for commands using ./ ( '.' is a shorthand for the current directory) path specifies that I am looking for the file '-' in the current working directory.
password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
## Level 2 → Level 3
We had to read a file called spaces in this filename located in the home directory for the password. So I tried this by using both single quotes and backticks between the words otherwise the each word in the file name would be considered as a different argument. 
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat 'spaces in this filename'
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
bandit2@bandit:~$ cat spaces\in\this\filename
cat: spacesinthisfilename: No such file or directory
bandit2@bandit:~$ cat spaces\ in\ this\ filename
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
## Level 3 → Level 4
password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
## Level 4 → Level 5
I ran the command `cd inhere` followed by `ls` to list the files in inhere directory.
```
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```
Since only one of them was in human readable form, I ran the command `file ./*c` to check the  file type for all the files.
```
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```
Then I catted ./-file07 to get the password.

reference: [File type of files in a directory](https://www.hostinger.in/tutorials/linux-file-command/)
password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
## Level 5 → Level 6
In this level the password for the next level was stored in a file somewhere under the inhere directory and had all of the following properties:
human-readable, 1033 bytes in size and not executable. I ran the command `find . -type f -size 1033c -exec cat {} \;`. Here, find command searches for a file of size 1033 bytes in the current directory, and executes cat command on every meeting the criteria.

password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
## Level 6 → Level 7
In this level the password for the next level was stored somewhere on the server and had all of the following properties: owned by user bandit7, owned by group bandit6, 33 bytes in size.

password:
## Level 7 → Level 8
password:
## Level 8 → Level 9
password:
