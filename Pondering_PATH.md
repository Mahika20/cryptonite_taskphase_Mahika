# Module 12: Pondering PATH
## Challenge 1: The PATH variable
This challenge required us to disrupt the operation of the /challenge/run program so that it cannot find the rm command. I ran the command `PATH=""` to set PATH to an empty string so that no command, including rm, can be found by the program. Then I ran the command `/challenge/run` which gave the folllowing output:
```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{Iiep3tyfFT8aqpp-xoot3gj0bw2.dZzNwUDL1YTN0czW}
```
Here /challenge/run couldn't find the rm command, which was located in one of the directories in the PATH variable, as PATH was blanked out.

Flag link: pwn.college{Iiep3tyfFT8aqpp-xoot3gj0bw2.dZzNwUDL1YTN0czW}
## Challenge 2: Setting Path
This challenge required us to run /challenge/run, having the win command, via its bare name located in the /challenge/more_commands/ directory. First step was to overwrite PATH with /challenge/more_commands/ directory. So I ran the command `PATH=/challenge/more_commands/` followed by `/challenge/run` which gave the following output:
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{owL45TzxmRofwx3IUHjmDIIRMRv.dVzNyUDL1YTN0czW}
```
Here, I did not have to execute the program via its path as PATH was set to the /challenge/more_commands/ directory and any command in it could be executed with its bare name.

Flag link: pwn.college{owL45TzxmRofwx3IUHjmDIIRMRv.dVzNyUDL1YTN0czW}
## Challenge 1: The PATH variable
This challenge required us to make a shell script called win, add its location to the PATH, and enable /challenge/run to find it. However, win command cannot cat the file if I overwrite PATH with the directory having win as cat command is also located in some directory in PATH. So, I tried creating a new directory for win to be stored in.

References: [Adding directories to path](https://unix.stackexchange.com/questions/462065/how-to-add-more-directiories-in-path)
Flag link: 
## Challenge 1: The PATH variable

Flag link: 
