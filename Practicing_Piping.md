# Module 6: Practicing Piping
## Challenge 1:
This challenge required us to use this input redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase). I ran the command `echo PWN > COLLEGE` to redirect the word PWN to the file COLLEGE. This step yielded the flag.

Flag link: pwn.college{w2ORS7e5fhxEIc3QG_YhFAWed72.dRjN1QDL1YTN0czW}
## Challenge 2:
This challenge required us to redirect the output of /challenge/run to the file myflag. So, I ran the command `/challenge/run >  myflag` which
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
## Challenge 4:

Flag link:
## Challenge 5:

Flag link:
## Challenge 6:

Flag link:
## Challenge 7:

Flag link:
## Challenge 8:

Flag link:
## Challenge 9:

Flag link:
## Challenge 10:

Flag link:
## Challenge 11:

Flag link:
## Challenge 12:

Flag link:
