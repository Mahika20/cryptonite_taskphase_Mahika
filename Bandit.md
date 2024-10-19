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
password:
## Level 5 → Level 6
password:
## Level 6 → Level 7
password:
## Level 7 → Level 8
password:
## Level 8 → Level 9
password:
