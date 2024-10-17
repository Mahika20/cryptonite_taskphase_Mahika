# Module 10: Untangling Users
## Challenge 1: Becoming the root with su
In this challenge, we were required to use the 'su' command to become the root user. I ran the command `su`. There was a prompt asking for password so I typed in hack-the-planet which was the password for only this challenge. Since, I had become the root user, I catted /flag and receieved the flag link.
```
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{MIpFah5dtVdENp4zrD_yufH4HwD.dVTN0UDL1YTN0czW}
```

Flag link: pwn.college{MIpFah5dtVdENp4zrD_yufH4HwD.dVTN0UDL1YTN0czW}
## Challenge 2: Other users with su
This challenge required us to switch to the zardus user and then run /challenge/run.I first ran the command `su zardus` to switch user to zardus. Then I entered the password dont-hack-me for authentication. Finally on running the command `/challenge/run`, I received the flag.
```
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{MNpTKmDdQwARFb6_MxDyz7JMqKs.dZTN0UDL1YTN0czW}
```

Flag link: pwn.college{MNpTKmDdQwARFb6_MxDyz7JMqKs.dZTN0UDL1YTN0czW}
## Challenge 3: Cracking Passwords
This challenge required us to crack the password from the file /challenge/shadow-leak and use the cracked password for authentication while switching to zardus user. I ran the command `john /challenge/shadow-leak` to load the password from the file /challenge/shadow-leak and John the ripper processed the hash and cracked the password. Then I ran the command `su zardus` to switch user to zardus and entered the cracked password for authentication. Finally, I ran `/challenge/run` to acccess the flag.
```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04911g/s 286.0p/s 286.0c/s 286.0C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{MbSSA94S7gXp0pewlTQs5WQCsDV.ddTN0UDL1YTN0czW}
```

Flag link: pwn.college{MbSSA94S7gXp0pewlTQs5WQCsDV.ddTN0UDL1YTN0czW}
## Challenge 4: Using sudo
This challenge required us to use sudo to read the flag. I ran the command `sudo cat /flag` to run the command cat /flag as the root without switching to root. This gave the following output:
```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{0OWnVhbxs-UQUOH9wDtes6x8WiB.dhTN0UDL1YTN0czW}
```
Flag link: pwn.college{0OWnVhbxs-UQUOH9wDtes6x8WiB.dhTN0UDL1YTN0czW}
