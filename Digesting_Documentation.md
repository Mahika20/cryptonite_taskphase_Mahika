# Module 4: Digesting Documentation
## Challenge 1: Learning from Documentation
In this challenge, we were required to invoke /challenge/challenge with the argument --giveflag to get the flag. 
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{kaXvcIQ2V8i9mkasEoELc7XyGNK.dRjM5QDL1YTN0czW}
```

Flag link: pwn.college{kaXvcIQ2V8i9mkasEoELc7XyGNK.dRjM5QDL1YTN0czW}
## Challenge 2: Learning complex usage
This challenge required us to retrieve the flag using the /challenge/challenge command. I first tried the command '/challenge/challenge -- printfile /challenge/DESCRIPTION.md' to get the description of the level then I ran the command '/challenge/challenge --printfile /flag' to print the contents of the flag file.
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{kKSK5MATMaCJfrByiit9y8qmGfc.dVjM5QDL1YTN0czW}
```

Flag link: pwn.college{kKSK5MATMaCJfrByiit9y8qmGfc.dVjM5QDL1YTN0czW}
## Challenge 3: Reading Manuals
This level required us to  find a secret option in the challenge and use it to print the flag. I ran the command `man challenge` to view the manual of challenge. It gave the following prompt:
```
CHALLENGE(1)                             Challenge Commands                             CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --yinsdc NUM
              print the flag if NUM is 459

AUTHOR
       Written by Zardus.
```
Then I ran the command '`/challenge/challenge --yinsdc 459` since according to the description given in the manual, the argument --yinsdc NUM would print the flag if NUM was 459. This yielded the flag.

Flag link: pwn.college{45C91yiP-R6EH12M1BUnK-sE8O1.dRTM4QDL1YTN0czW}
## Challenge 4: Searching Manuals
This challenge required us to search the flag in the challenge man page. I ran the command `man challenge` to get the challenge manual. Once the manual was displayed, I searched for the flag file using '/file'. I went through the results using N to go to the previous results and n to check the next results. I found the argument which would give the flag: --rmj, and finally ran the command `/challenge/challenge --rmj`. This yileded the flag

Flag link: pwn.college{EkONHUEeOSeXGL3gomi_cbrKkWF.dVTM4QDL1YTN0czW}
## Challenge 5:  Seaching for manuals
This challenge required us to find the hidden challenge man page which had the flag. I started off with running the 'man man' command to read the man page manual page. It had the following commands in the synopsis: 
```
SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...
```
So, I ran the command `man -k challenge` to display the manpages having the word challenge.
```
hacker@man~searching-for-manuals:~$ man -k challenge
wnuajdczab (1)       - print the flag!
```
Then I ran the command `man wnuajdczab` to get the manpage of wnuajdczab. It gave the following result:
```
SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --wnuajd NUM
              print the flag if NUM is 869
```
The command --wnuajd NUM would print the flag. So I ran the command `/challenge/challenge --wnuajd 869` and received the flag.

Flag link:pwn.college{wnuWRVTT8aDYATIHK6943MjUBHE.dZTM4QDL1YTN0czW}
## Challenge 6: Helpful programs
This challenge required us to read a program's documentation with --help. I ran the command `/challenge/challenge --help`. The output provided the arguments that could be passed to the program and other information:
```
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
I ran the command `/challenge/challenge -p` as the argument -p would get the value for -g GIVE_THE_FLAG argument. The output was `The secret value is: 127`. So, I ran the command `/challenge/challenge -g 127` which yielded the flag.

Flag link: pwn.college{s12D-7junUyXzz5nUOAreIy5rtC.ddjM4QDL1YTN0czW}
## Challenge 7: Help for builtins
I started off with the command `help challenge` to get help for the shell builtin challenge command. It gave the following output:
```
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "w4OqU8HF".
```
Here, the argument --secret VALUE	prints the flag. So, I ran the command `challenge --secret w4OqU8HF` to get the flag

Flag link: pwn.college{w4OqU8HF5O51MVNV1yGMli-KqMX.dRTM5QDL1YTN0czW}

