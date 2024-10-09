# Module 6: Practicing Piping
## Challenge 1:
This challenge required us to use this input redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase). I ran the command `echo PWN > COLLEGE` to redirect the word PWN to the file COLLEGE. This step yielded the flag.

Flag link: pwn.college{w2ORS7e5fhxEIc3QG_YhFAWed72.dRjN1QDL1YTN0czW}
## Challenge 2: Redirecting more output
This challenge required us to redirect the output of /challenge/run to the file myflag. So, I ran the command `/challenge/run >  myflag` which redirected the output of /challenge/run to myflag. This gave the following output:
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
I finally ran the command `cat myflag` and got the flag.

Flag link:  pwn.college{kR-3wBNCB2gOgyb_cnbNYVo2G0v.dVjN1QDL1YTN0czW}
## Challenge 3: Appending Output
Thsi challenge required us to run /challenge/run with an append-mode to redirect the output to the file /home/hacker/the-flag. So, I ran the command `/challenge/run >> /home/hacker/the-flag` to redirect the output of /challenge/run to /home/hacker/the-flag. Here, I used >> to append the content. Then I ran the comman `cat /home/hacker/the-flag` which gave the following output: 
```
 | 
\|/ This is the first half:
 v 
pwn.college{A-D3FygpzI2PbSGWYGhLo4_-qtb.ddDM5QDL1YTN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```
This indicated that I correctly redirected the output as the second half of the flag was appended to the first half instead of overwriting it.

Flag link: pwn.college{A-D3FygpzI2PbSGWYGhLo4_-qtb.ddDM5QDL1YTN0czW}
## Challenge 4: Redirecting Errors
This challenge required us to to redirect the output of /challenge/run to myflag, and the errors to instructions. So I ran the command `/challenge/run > myflag 2>instructions` to redirect the flag to myflag file and the errors to instructions. Since everything was redirected, nothing was printed. Then I ran the command  `cat myflag` which printed the flag.

Flag link: pwn.college{wqCr4ov-KCbMdvv2TLd40a0oAgL.ddjN1QDL1YTN0czW}
## Challenge 5: Redirecting Input
This challenge required us to redirect the PWN file to /challenge/run and have the PWN file contain the value COLLEGE. First, I entered the command `echo COLLEGE> PWN` to write the 'COLLEGE' to the PWN file. Then in order to redirect the input of PWN to /challenge/run, I ran the command ` /challenge/run < PWN` which yielded the flag.

Flag link: pwn.college{YcugZX2pz7SR2aIzEkqJWYHzsdM.dBzN1QDL1YTN0czW}
## Challenge 6: Grepping Stored Results
I first ran the command `/challenge/run > /tmp/data.txt` to redirect the output of /challenge/run to /tmp/data.txt. This gave the following prompt:
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```
Then in order to get the flag I ran the command ` grep pwn.college /tmp/data.txt` as the flag contains the substring 'pwn.college'. This command would search for text containing the provided substring. Finally the flag was retrieved. 


Flag link: pwn.college{YYp000txc-H7RrlidpBBADhcYsu.dhTM4QDL1YTN0czW}
## Challenge 7: Grepping live output
This challenge required us to use the pipe operator (|) to avoid the need to store results to a file and get the flag from /challenge/run. So, I ran the command `/challenge/run | grep pwn.college` which connected the output from the command on the left side to the input of the command on the right side. This returned the following prompt:
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{AhEJSRis8YVtgdkKXNafmoKKoY1.dlTM4QDL1YTN0czW}
```

Flag link: pwn.college{AhEJSRis8YVtgdkKXNafmoKKoY1.dlTM4QDL1YTN0czW}
## Challenge 8: Grepping Errors
This challenge required us to grep through errors directly 
I ran the command `/challenge/run 2>& 1 | grep pwn.college`. Here, I used 2>& 1 to redirect standard error to standard output and searched for the flag using the substring pwn.college. This returned the following promp
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{k70fD8YIu5b0uOPmp04rT4MYnVj.dVDM5QDL1YTN0czW}
```

Flag link: pwn.college{k70fD8YIu5b0uOPmp04rT4MYnVj.dVDM5QDL1YTN0czW}
## Challenge 9: Duplicating piped data with tee
This challenge required us to pipe /challenge/pwn into /challenge/college but first intercept the data to see what pwn needs. I ran the command
`/challenge/pwn | tee flag | /challenge/college`. Here, I used tee to find what pwn needed and this gave the following output:
```
Processing...
WARNING: you are overwriting file flag with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat flag
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "EYpL4EC0"
```
Here the secret argument to be passed and onformation on how it was to be passed was provided. So, I ran the command `/challenge/pwn --secret EYpL4EC0| /challenge/college` to  pipe the output to /challenge/college. This gave the following output: 
```
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{EYpL4EC09HM3LB2Smf_tE-s_eal.dFjM5QDL1YTN0czW}
```

Flag link: pwn.college{EYpL4EC09HM3LB2Smf_tE-s_eal.dFjM5QDL1YTN0czW}
## Challenge 10: Writing to multiple programs
This challenge required us to run the /challenge/hack command, and duplicate its output as input to both the /challenge/the and the /challenge/planet commands. So I ran the command `/challenge/hack | tee >( /challenge/the ) >( /challenge/planet )`  to redirect the output to the two commands simultaneously using process substitution. This step gave the following output: 
```
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
72479118635318356
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{kqs94j-enKdo8_qQ7g5-yiF6W4A.dBDO0UDL1YTN0czW}
```
Flag link: pwn.college{kqs94j-enKdo8_qQ7g5-yiF6W4A.dBDO0UDL1YTN0czW}

## Challenge 11: Split-piping stderr and stdout
This challenge required us to redirect hack's stderr to /challenge/the and redirect hack's stdout to /challenge/planet. To do so, I ran the command `/challenge/hack > >( /challenge/planet ) 2> >( /challenge/the )` 

Flag link: pwn.college{IIg3db9yd67hxxSNNjsYqjs2YLx.dFDNwYDL1YTN0czW}
