# Module 9: Perceiving Permissions
## Challenge 1: Changing file ownership
In this challenge we could use chown as the hacker user and we had to change the owner of the /flag file to the hacker user, and then the flag.
I ran the command ` chown hacker /flag`. Generally, chown can only be invoked by the root user but in this level we could use hacker. This command changed the ownership of /flag file to hacker. Then I ran the command `cat /flag` to read the content of the flag. This step yielded the flag. I also ran the commands `ls -l /flag` and `ls -l` to have a look at the permissions for /flag file and all the files respectively.
```
hacker@permissions~changing-file-ownership:~$ ls -l /flag
-r-------- 1 hacker root 58 Oct 15 15:29 /flag
hacker@permissions~changing-file-ownership:~$ ls -l
total 52
-rw-r--r-- 1 hacker hacker    4 Oct  7 23:01 COLLEGE
drwxr-xr-x 2 hacker hacker 4096 Sep 30 14:41 Desktop
-rw-r--r-- 1 hacker hacker   19 Oct 14 19:18 PWN
-rw-r--r-- 1 hacker hacker   30 Oct  1 17:39 README.md
-rw-r--r-- 1 hacker hacker  194 Oct  9 15:27 college
-rw-r--r-- 1 hacker hacker   19 Oct 14 19:15 flag
-rw-r--r-- 1 root   hacker   58 Oct  7 11:50 h
-rw-r--r-- 1 hacker hacker  829 Oct  8 13:09 instructions
drwxr-xr-x 2 hacker hacker 4096 Oct  5 18:00 my_directory
-rw-r--r-- 1 hacker hacker   93 Oct  9 17:21 myflag
lrwxrwxrwx 1 hacker hacker    5 Oct  6 16:29 not-the-flag -> /flag
-rw-r--r-- 1 hacker hacker  169 Oct  8 20:02 planet
-rw-r--r-- 1 hacker hacker  169 Oct  8 20:02 the
-rw-r--r-- 1 hacker hacker  435 Oct  8 12:16 the-flag
```
Reference: [geeksforgeeks](https://www.geeksforgeeks.org/chown-command-in-linux-with-examples/)
Flag link: pwn.college{kpX7nLg4tWj1eHo0AwOI8yrxNFN.dFTM2QDL1YTN0czW}
## Challenge 2: Groups and files
This challlenge required us to to invoke chgrp as the hacker user. I ran the command `chgrp hacker /flag` to change the group ownership of flag file file from root to hacker. Then on running the command `cat /flag`, the flag was given. `hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{wfubIw0gQplJ7qAuamkRBgAshre.dFzNyUDL1YTN0czW}`. I also ran the command ` ls -l /flag` to check the permissions for /flag file which gave the following output:
```
hacker@permissions~groups-and-files:~$ ls -l /flag
-r--r----- 1 root hacker 58 Oct 15 17:57 /flag
```

Flag link: pwn.college{wfubIw0gQplJ7qAuamkRBgAshre.dFzNyUDL1YTN0czW}
## Challenge 3: Fun with group names
This challenge required us to use chgrp to the randomized name of the group that our user is in to get the flag. I first used `id` command to find out my user and group information. 
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp18088) groups=1000(grp18088)
```
Since the group name is grp18088, I tried the command `chgrp grp18088 /flag`  to change the group to grp18088. Fianlly, I catted /flag and got the flag.
```
hacker@permissions~fun-with-groups-names:~$ chgrp grp18088 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{cay3SUr2i3Jt9MGgsmJYLyDIIK6.dJzNyUDL1YTN0czW}
```
I also ran the command `ls -l` to have a look at the groups and permissions for the files:
```
hacker@permissions~fun-with-groups-names:~$ ls -l
total 52
-rw-r--r-- 1 hacker grp18088    4 Oct  7 23:01 COLLEGE
drwxr-xr-x 2 hacker grp18088 4096 Sep 30 14:41 Desktop
-rw-r--r-- 1 hacker grp18088   19 Oct 14 19:18 PWN
-rw-r--r-- 1 hacker grp18088   30 Oct  1 17:39 README.md
-rw-r--r-- 1 hacker grp18088  194 Oct  9 15:27 college
-rw-r--r-- 1 hacker grp18088   19 Oct 14 19:15 flag
-rw-r--r-- 1 root   grp18088   58 Oct  7 11:50 h
-rw-r--r-- 1 hacker grp18088  829 Oct  8 13:09 instructions
drwxr-xr-x 2 hacker grp18088 4096 Oct  5 18:00 my_directory
-rw-r--r-- 1 hacker grp18088   93 Oct  9 17:21 myflag
lrwxrwxrwx 1 hacker grp18088    5 Oct  6 16:29 not-the-flag -> /flag
-rw-r--r-- 1 hacker grp18088  169 Oct  8 20:02 planet
-rw-r--r-- 1 hacker grp18088  169 Oct  8 20:02 the
-rw-r--r-- 1 hacker grp18088  435 Oct  8 12:16 the-flag
```
Here, I made the observation that the group name is different from the owner name unlike challenge1(Changing file ownership), where the group name and owners were same in most cases, that is, "hacker".

Flag link: pwn.college{cay3SUr2i3Jt9MGgsmJYLyDIIK6.dJzNyUDL1YTN0czW}
## Challenge 4: Changing Permissions
This challeneg required us to change the permissions of the /flag file to read it. Generally we need to have write access to the file in order to change its permissions but for this level, we could chmod anything even as the hacker user. I started off by running the command `ls -l /flag` to display the permissions and groups for /flag file. `hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 58 Oct 16 20:15 /flag`. Here, the read acccess is available only for user. So, I ran the command `chmod g+r /flag` followed by ` ls -l /flag` to add read access for groups too: `hacker@permissions~changing-permissions:~$ chmod g+r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r--r----- 1 root root 58 Oct 16 20:15 /flag`. Then, I tried catting /flag to see if it gives the flag, but it  gave the prompt: `cat: /flag: Permission denied`. So, I ran the command `chmod a+r /flag` to add read access for all users and then received the flag by catting /flag.
```
hacker@permissions~changing-permissions:~$ chmod a+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{MqTMe7aH9SPDg5EdVDK9RgbTVVz.dNzNyUDL1YTN0czW}
```
I also tried the `chmod a-r /flag` commmand to remove read permissions for all users then ran than command `chmod gou+r /flag` to again add the read accesss for all users. Finally, I received the flag again by catting /flag.
```
hacker@permissions~changing-permissions:~$ chmod a-r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
---------- 1 root root 58 Oct 16 20:15 /flag
hacker@permissions~changing-permissions:~$ chmod gou+r /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r--r--r-- 1 root root 58 Oct 16 20:15 /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{MqTMe7aH9SPDg5EdVDK9RgbTVVz.dNzNyUDL1YTN0czW}
```

Flag link: pwn.college{MqTMe7aH9SPDg5EdVDK9RgbTVVz.dNzNyUDL1YTN0czW}
## Challenge 5: Executable Files
This challenge required us to run /challenge/run program by making it executable.
I ran the command ran the command `ls -l /challenge/run` to have a look at the groups and permissions for /challenge/run. `hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul  4 06:37 /challenge/run`. Then I ran the command `chmod a+x  /challenge/run` to add execute permissions for all users to make it executable.
```
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{YbuOV5hDohh-8xXQmPMEO2etzWw.dJTM2QDL1YTN0czW}
```

Flag link: pwn.college{YbuOV5hDohh-8xXQmPMEO2etzWw.dJTM2QDL1YTN0czW}
## Challenge 6: Permission Tweaking Practice
This challenge required us to change the permissions of the /challenge/pwn file in specific ways a few times in a row. I launched /challenge/run to get started which gave the following instructions as a prompt:
```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
```
I ran the command `chmod go+x /challenge/pwn` to set execute permission to group and others (here world).
```hacker@permissions~permission-tweaking-practice:~$ chmod go+x /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw-r-xr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
Then in order to remove execute permission for world, I ran the command ` chmod o-x /challenge/pwn`.
```
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rw-r-xr--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
For this round, I had to remove the execute permissions for group also. So, I ran the command ` chmod g-x /challenge/pwn`.
```
hacker@permissions~permission-tweaking-practice:~$ chmod g-x /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r--rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
```
Now, I had to run the `chmod o+wx /challenge/pwn` command to add write and execute permission for world.
```
hacker@permissions~permission-tweaking-practice:~$ chmod o+wx /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": rw-r--rwx
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxr-xrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
```
Then the command `chmod ug+x /challenge/pwn` to add execute permissions tfor user and group.
```
hacker@permissions~permission-tweaking-practice:~$ chmod ug+x /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": rwxr-xrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
```
Then I ran the command `chmod g+w /challenge/pwn ` to add write permission to group.
```
hacker@permissions~permission-tweaking-practice:~$ chmod g+w /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": rwxrwxrwx
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xrwxrwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
```
For this round, I ran the command `chmod u-w /challenge/pwn` to remove write permissions for user.
```
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": r-xrwxrwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-x-wxrwx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
* the world does have execute permissions
```
Then I ran `chmod g-r /challenge/pwn` to remove read access for group.
```
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
```
Finally I ran the command ` chmod a+r /flag` to add read permissions for all users and catted /flag which yielded the flag.

Flag link: hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{YofoD3ffd6jWu4BKqxoWpx6beHY.dBTM2QDL1YTN0czW}
## Challenge 7: Permission Setting Practice

Flag link:
## Challenge 8: Changing file ownership

Flag link:

