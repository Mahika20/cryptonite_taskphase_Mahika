# Module 3: Shell Variables
## Challenge 1: Printing Variables
In this challenge, the flag was put into a variable names "FLAG". We were required to make our shell print the flag. I ran the command: `echo $FLAG`. Here, echo is used to access and print the content of variable FLAG by prepending FLAG with $.
```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{McARzUjn_WHe4vm4wOKGG2K5bN1.ddTN1QDL1YTN0czW}
```
Flag link: pwn.college{McARzUjn_WHe4vm4wOKGG2K5bN1.ddTN1QDL1YTN0czW}
## Challenge 2: Setting Variables
This challenge required us to set the PWN variable to the value COLLEGE. So I ran the command `PWN=COLLEGE`. Here, $ is not used as the variable is not being accessed. This step gave the following prompt:
```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{0BRV6lC1c7VI_jR7eoqjE--ZIbb.dlTN1QDL1YTN0czW}
```

Flag link: pwn.college{0BRV6lC1c7VI_jR7eoqjE--ZIbb.dlTN1QDL1YTN0czW}
## Challenge 3: Multi-word Variables
This challenge required us to set the variable PWN to COLLEGE YEAH. COLLEGE YEAH is a multi-word variable which has to be set encased in double quotes to be set to a variable otherwise YEAH would be considered a command. So, I ran the following command `PWN="COLLEGE YEAH"`. This gave the following prompt:
```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{Uks3oy7GYkhHzxBGdP3tDNeD4Pn.dBjN1QDL1YTN0czW}
```

Flag link: pwn.college{Uks3oy7GYkhHzxBGdP3tDNeD4Pn.dBjN1QDL1YTN0czW}
## Challenge 4: Exporting Variables
This challenge required us to invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported. So I started with the command `export PWN` followed by `PWN=COLLEGE` to export PWN and set the value to COLLEGE.
```
hacker@variables~exporting-variables:~$ export PWN
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
```
Then I ran the command `COLLEGE=PWN` without exporting COLLEGE.
```
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
```
Finally, I ran the `/challenge/run` command which gave the follwoing output:
```
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{ArBt2bshWr8fO9SYb3TUxsS_X0k.dJjN1QDL1YTN0czW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value
```

Flag link: pwn.college{ArBt2bshWr8fO9SYb3TUxsS_X0k.dJjN1QDL1YTN0czW}
## Challenge 5: Printing Eported Variables
This challenge required us to make use of the env command to print out every exported variable set in our shell. I ran the command `env` which gave the following output:
```
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
DOJO_AUTH_TOKEN=56ed78c64736950d1e9087838e75689176616d79eac387f7d811e312f12b6cf2
HOME=/home/hacker
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
FLAG=pwn.college{QBbD0gP7HFyTGQeltMBiXYad1Qb.dhTN1QDL1YTN0czW}
LESSCLOSE=/usr/bin/lesspipe %s %s
TERM=xterm
LESSOPEN=| /usr/bin/lesspipe %s
SHLVL=1
LC_CTYPE=C.UTF-8
PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/run/workspace/bin/env
```
Since the output was really long, I searched for the flag using the command `env | grep FLAG`  which redirected the output of the env command to the input of the command grep FLAG. This step yielded the flag.

Flag link: FLAG=pwn.college{QBbD0gP7HFyTGQeltMBiXYad1Qb.dhTN1QDL1YTN0czW}
## Challenge 6: Storing command Output
This challenge required us to use command substitution to read the output of the /challenge/run command directly into a variable called PWN. We can use $() or `` to encase the command while assigning it to a variable, but backticks are not preffered as we cannot do nested command substitution with it. So, I ran the command `PWN=$(/challenge/run)`. It gave the output as follows:
```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
```
In order to read print the output I ran the command `echo $PWN` which yielded the flag.

Flag link: pwn.college{s2BMex4fGRCJOYPjmkriQNjd-Sy.dVzN0UDL1YTN0czW}
## Challenge 7: Reading Input
This challenge required us to use read to set the PWN variable to the value COLLEGE. I ran the command `read -p "INPUT: " PWN` to read the value to the variable PWN and I also set the prompt to "INPUT: " using the -p argument to make it easier to understand.
```
hacker@variables~reading-input:~$  read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wzpqlApQnZuOTW6cx_cBfVTx6jo.dhzN1QDL1YTN0czW}
```

Flag link: pwn.college{wzpqlApQnZuOTW6cx_cBfVTx6jo.dhzN1QDL1YTN0czW}
## Challenge 8: Reading Files
This challenge required us to read /challenge/read_me into the PWN environment variable. So I ran the command `read PWN < /challenge/read_me` to redirect the /challenge/read_me file to the PWN variable and to read PWN.
```
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{I5HXZjTUPjf2LD2LByoMWh73PKw.dBjM4QDL1YTN0czW}
```

Flag link: pwn.college{I5HXZjTUPjf2LD2LByoMWh73PKw.dBjM4QDL1YTN0czW}


