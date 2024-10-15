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
## Challenge 2: Killing processes
This challenge required us to find the dont_run process and kill it to run the /challenge/run commmand. I first ran the command `ps -ef` to list the processes:
```
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 08:12 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default
root           7       1  0 08:12 ?        00:00:00 /run/dojo/bin/sleep 6h
root          71       1  0 08:12 ?        00:00:00 su -c /challenge/.launcher hacker
hacker        73      71  0 08:12 ?        00:00:00 /challenge/dont_run
hacker        74      73  0 08:12 ?        00:00:00 sleep 6h
hacker        75       0  0 08:12 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        92      75  0 08:13 pts/0    00:00:00 ps -ef
```
In the given output, the PID of /challenge/dont_run command is 73 so I ran the command `kill  73 `. Then, by running the command `/challenge/run` the output was:
```
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{oMp7OB75sgjsMEd4FdN9-A2vxxf.dJDN4QDL1YTN0czW}
```

Flag link: pwn.college{oMp7OB75sgjsMEd4FdN9-A2vxxf.dJDN4QDL1YTN0czW}
## Challenge 3: Interrupting processes
This challenge required us to interrupt /challenge/run. I first ran the command `/challenge/run` which gave the following output:
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
```
So, I use Ctrl+C key combination to get interrupt the process.`^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{kBuN-J81ZIFqli5Vh-XKKzpYu_P.dNDN4QDL1YTN0czW}`

Flag link: pwn.college{kBuN-J81ZIFqli5Vh-XKKzpYu_P.dNDN4QDL1YTN0czW}
## Challenge 4: Suspending processes
This challenge required us to launch run, suspend it, then launch another copy while the first is suspended. First I ran the command `/challenge/run`.
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         100      65  0 11:38 pts/1    00:00:00 bash /challenge/run
root         102     100  0 11:38 pts/1    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
```
Then, in order to suspend the process in the background, I used the Ctrl+Z combination which gave the following output:
```
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$  /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         100      65  0 11:38 pts/1    00:00:00 bash /challenge/run
root         107      65  0 11:38 pts/1    00:00:00 bash /challenge/run
root         109     107  0 11:38 pts/1    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{MsRxgysVtL35KRGGGLogoSrdTF7.dVDN4QDL1YTN0czW}
```

Flag link: pwn.college{MsRxgysVtL35KRGGGLogoSrdTF7.dVDN4QDL1YTN0czW}
## Challenge 5: Resuming processes
This challenge required us to suspend run, then resume it. I ran the command `/challenge/run` which gave the following output:
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
```
Then in order to suspend it, I  I used the Ctrl+Z combination followed by the fg command to resume it in the foreground.
```
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{8VSj9e3maAlTmVSWJn_6lbLckjf.dZDN4QDL1YTN0czW}
Don't forget to press Enter to quit me!

Goodbye!
```
Flag link: pwn.college{8VSj9e3maAlTmVSWJn_6lbLckjf.dZDN4QDL1YTN0czW}
## Challenge 6: Listing processes
This challenge required us to execute a copy of run in the bakcground. I did this by first running the command `/challenge/run`.
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
```
Then in order to suspend it, I used the Ctrl+Z key combination followed by the bg command to resume it in the background. Then, rerunning the `/challenge/run` gave the following output:
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{k1RIEjAC7GbYC_mBg9VtA1AzyJW.ddDN4QDL1YTN0czW}
```

Flag link: pwn.college{k1RIEjAC7GbYC_mBg9VtA1AzyJW.ddDN4QDL1YTN0czW}
## Challenge 7: Foregrounding processes
I ran the command `/challenge/run` which gave the instructions for this level. 
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
```
This task required us to suspend /challenge/run, resume it in the background, and then foreground it. So, I used the Ctrl+Z key combination followed by the bg command to resume it in the background. Then I finally ran the fg command to bring thr process to the foreground. 
```
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{4qh75buBY6K7cJDP0CTmzny5Re_.dhDN4QDL1YTN0czW}
```

Flag link: pwn.college{4qh75buBY6K7cJDP0CTmzny5Re_.dhDN4QDL1YTN0czW}
## Challenge 8: Starting Backgrounded Processes
This task required us to run /challenge/run directly in the background. To run the process in the background, & should be appended after the command but, initially I made the mistake of not using it and it gave this prompt:
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run
You've started me in the foreground! You must start me in the background (by 
appending '&' to the command) to get the flag!
```
Then I ran the correct command `/challenge/run &` which gave the following output:
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 88
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{IYAwuUKU-_2eytq8sU2GJlsXfQg.dlDN4QDL1YTN0czW}

```
Flag link: pwn.college{IYAwuUKU-_2eytq8sU2GJlsXfQg.dlDN4QDL1YTN0czW}
## Challenge 9: Processes Exit codes
This task required us to retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument. So I first ran ` /challenge/get-code` followed by `echo $?` to read and print the value of ? which is a special variable holding the exit code.
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
192
```
Then I ran the command `/challenge/submit-code 192` where 192 is the error code. This step yielded the flag.
```
hacker@processes~process-exit-codes:~$ /challenge/submit-code 192
CORRECT! Here is your flag:
pwn.college{I62Kwy1AsMYkks39LSySXio3N63.dljN4UDL1YTN0czW}
```

Flag link: pwn.college{I62Kwy1AsMYkks39LSySXio3N63.dljN4UDL1YTN0czW}
