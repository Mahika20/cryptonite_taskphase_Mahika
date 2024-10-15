# Module 8: Proccess and jobs
## Challenge 1: Listing processes
This challenge required us to find renamed /challenge/run command in the running process list, figure out the filename, and relaunch it directly for the flag. I tried both the methods `ps -ef` and `ps aux` to list processes. The output for ps -ef was:
```
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 07:51 ?        00:00:00 /sbin/docker-init -- /nix/va
root           7       1  0 07:51 ?        00:00:00 /run/dojo/bin/sleep 6h
root          68       1  0 07:51 ?        00:00:00 /challenge/5123-run-30701
root          72      68  0 07:51 ?        00:00:00 sleep 6h
hacker        73       0  0 07:54 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        90      73  0 07:54 pts/0    00:00:00 ps -ef
```
and the output for ps aux was:
```
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   07:51   0:00 /sbin/docker-
root           7  0.0  0.0   5052  2560 ?        S    07:51   0:00 /run/dojo/bin
root          68  0.0  0.0   4132  2560 ?        S    07:51   0:00 /challenge/51
root          72  0.0  0.0   2744  1600 ?        S    07:51   0:00 sleep 6h
hacker        73  0.0  0.0   5360  3840 pts/0    Ss   07:54   0:00 /run/dojo/bin
hacker        91  0.0  0.0   7868  3520 pts/0    R+   07:55   0:00 ps aux
```
The -ef argument printed the commands in their full format while aux printed commands in a user-friendly manner. So, when I tried running the renamed challenge command that is `/challenge/51` from the output of ps aux, the output was:
```
hacker@processes~listing-processes:~$ /challenge/51
ssh-entrypoint: /challenge/51: No such file or directory
```
Whereas, running the command from the output from ps -ef, that is  `/challenge/5123-run-30701`, gave the flag.
```
hacker@processes~listing-processes:~$ /challenge/5123-run-30701
Yahaha, you found me! Here is your flag:
pwn.college{wvJp_oXdINbBoVljnOnhvHaXk-7.dhzM4QDL1YTN0czW}
Now I will sleep for a while (so that you could find me with 'ps').
```
Flag link: pwn.college{wvJp_oXdINbBoVljnOnhvHaXk-7.dhzM4QDL1YTN0czW}
## Challenge 1: Listing processes
This challenge required us to find the dont_run process and kill it to run the /challenge/run commmand.
Flag link: pwn.college{oMp7OB75sgjsMEd4FdN9-A2vxxf.dJDN4QDL1YTN0czW}
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
## Challenge 1: Listing processes

Flag link:
