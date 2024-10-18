# Module 11: Chaining Commands
## Challenge 1: Chaining with semicolons
This challenge required us to run /challenge/pwn and then /challenge/college, chaining them with a semicolon. I ran the command `/challenge/pwn;/challenge/college` to chain the two commands using a semicolon. Here, semicolon allows us to write two commands before anything is executed. This step yielded the flag.
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{8WHe3oPV7gzZmkfo72tv8URSBoG.dVTN4QDL1YTN0czW}
```
Flag link: pwn.college{8WHe3oPV7gzZmkfo72tv8URSBoG.dVTN4QDL1YTN0czW}
## Challenge 2: Your first shell script
thsi challenge required us to run /challenge/pwn and then /challenge/college, but this time in a shell script called x.sh, then run it with bash. I ran the command `touch x.sh` to create a shellscript x.sh. Then I ran the command `echo "/challenge/pwn;/challenge/college" > x.sh` to print the output of both the commands /challenge/pwn and /challenge/college by chaining them with ';' and redirected it to x.sh. Then I ran the command `bash x.sh` which read the commands from the file x.sh. This step yielded the flag:
```
hacker@chaining~your-first-shell-script:~$ touch x.sh
hacker@chaining~your-first-shell-script:~$ echo "/challenge/pwn;/challenge/college" > x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{gySOUa9CJAcrjeCXyGlvNtBwE3h.dFzN4QDL1YTN0czW}
```

Flag link: pwn.college{gySOUa9CJAcrjeCXyGlvNtBwE3h.dFzN4QDL1YTN0czW}
## Challenge 3: Redirecting Script Output
This challenge again required us to run /challenge/pwn and then /challenge/college in a shell script and pipe the output of the script into a single invocation of the /challenge/solve command.  I ran the command `touch x.sh` to create a shellscript x.sh. Then I ran the command `echo "/challenge/pwn;/challenge/college" > x.sh` to print the output of both the commands /challenge/pwn and /challenge/college by chaining them with ';' and redirected it to x.sh. In order to pipe the output of bash x.sh command, I ran the command `bash x.sh| /challenge/solve`.
```
hacker@chaining~redirecting-script-output:~$ touch x.sh
hacker@chaining~redirecting-script-output:~$ echo "/challenge/pwn;/challenge/college" > x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh| /challenge/solve
Correct! Here is your flag:
pwn.college{sJteMiCGj6KUyZSlYdaStOCJguW.dhTM5QDL1YTN0czW}
```

Flag link: pwn.college{sJteMiCGj6KUyZSlYdaStOCJguW.dhTM5QDL1YTN0czW}
## Challenge 4: Executable Shell Scripts
This challenge required us to make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash. I ran the command `touch a.sh` to create a shellscript a.sh. Then I ran the command `echo "/challenge/solve"> a.sh` to print the output of the command /challenge/solve and redirected it to a.sh. Then I ran the command `chmod a+x a.sh` to make a.sh executable by setting all suer permissions to execute. Then I used the relative path ` ./a.sh` to run the shellscript. This step yielded the flag.
```
hacker@chaining~executable-shell-scripts:~$ touch a.sh
hacker@chaining~executable-shell-scripts:~$ echo "/challenge/solve"> a.sh
hacker@chaining~executable-shell-scripts:~$ chmod a+x a.sh
hacker@chaining~executable-shell-scripts:~$ ls
COLLEGE  README.md  flag          my_directory  planet    x
Desktop  a.sh       h             myflag        the       x.sh
PWN      college    instructions  not-the-flag  the-flag
hacker@chaining~executable-shell-scripts:~$ /a.sh
ssh-entrypoint: /a.sh: No such file or directory
hacker@chaining~executable-shell-scripts:~$ ./a.sh
Congratulations on your shell script execution! Your flag:
pwn.college{8RLEzi94iaIl6_pXApiKZEExQtr.dRzNyUDL1YTN0czW}
```

Flag link: pwn.college{8RLEzi94iaIl6_pXApiKZEExQtr.dRzNyUDL1YTN0czW}
