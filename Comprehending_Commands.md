# Module 3: Comprehending Commands
## Challenge 1: Cat not the pet but the command
In this challenge, I had to use the cat command to read the flag in the home directory. Since I was already in the home directory, I ran the command `cat flag` and received the flag.

Flag link: pwn.college{siugmP07oFB48BuaRkyA36dZhj6.dFzN1QDL1YTN0czW}
## Challenge 2: Catting absolute paths
For this challenge I used the command `cat /flag` to read the flag with cat at its absolute path /flag.

Flag link: pwn.college{s6b4NWL7xNvwSPTA4Wu5FLObnls.dlTM5QDL1YTN0czW}
## Challenge 3: More catting practice
This challenge required us to retrieve the flag, hidden in a different directory, by the absolute path. The absolute path of the file was provided in the instructions in terminal. I used the command 
`cat /lib/x86_64-linux-gnu/libcanberra-0.30/flag`
to retrieve the flag.

Flag link: pwn.college{ohVn40PHnaHJlh3OAoi2RACmSKX.dBjM5QDL1YTN0czW}
## Challenge 4: Grepping for a needle in a haystack
This challenge required us to search the file for lines of text containing the substring 'pwn.college' and print them. So, I ran the command `grep pwn.college /challenge/data.txt` to search for the flag. This step yielded the flag.

Flag link: pwn.college{YTpYgDDgWmK0YmZzIcRTyHWbTuh.ddTM4QDL1YTN0czW}
## Challenge 5: Listing files
This challenge required us to list the files in /challenge to find /challenge/run. So I ran the command `ls /challenge` to list the files in /challenge. It listed the following files: `2462-renamed-run-4017 DESCRIPTION. md`. I ran the command `cd /challenge` to access the challenge directory. Then I ran the command `/challenge/2462-renamed-run-4017` to get flag.

Flag link: pwn.college{kWsB9aIEuaOLmi8HDOhkXkqhQL7.dhjM4QDL1YTN0czW}
## Challenge 6:  Touching Files
Thsi challenge required us to create two files: /tmp/pwn and /tmp/college, and run /challenge/run. I ran the command `cd /tmp` to change the directory to /tmp. Then I ran the command `touch /tmp/college` followed by `touch /tmp/pwn` to create the files in tmp. Then I ran the command `\challenge\run` to get the flag.

Flag link: pwn.college{sx7Cdb_dkojRsuBDZmqXoP3I5o0.dBzM4QDL1YTN0czW}
## Challenge 7: Removing Files
This challenge required us to delete the delete_me file in our home directory, then run /challenge/check. I ran the command `rm delete_me` to remove the file. Then I changed the directory to challenge by `cd /challenge` and finally ran the command `/challenge/check` which checked the removal and provided the flag.

Flag link: pwn.college{w9CmldOpcA3hxh0z1gKtaZjLwdg.dZTOwUDL1YTN0czW}
## Challenge 8: Hidden files
This challenge required us to find the hidden flag file in /. I ran the command cd / to access / directory. In order to view all the files, including the hidden ones, I ran the command ls ~a. There I found the dot-prepended flag file -> /.flag-19271559011509. Then to receive the flag, I ran the command 
`grep pwn.college /.flag-19271559011509`

Flag link: pwn.college{YY6mK3In_zfAUYo_g3ytI9WPH9g.dBTN4QDL1YTN0czW}
## Challenge 9: An Epic Filesystem Quest
This task required us to find the flag by following a series of clues. I first got into the / directory using cd / and then enetered the command ls to view the files. The following files were shown: 
```
EVIDENCE  challenge  flag  lib32   media  opt   run   sys  var
bin       dev        home  lib64   mnt    proc  sbin  tmp
boot      etc        lib   libx32  nix    root  srv   usr
```
Then I ran the command cat EVIDENCE as it lloked like a hint and got the clue. The next clue was in: /usr/lib/python3/dist-packages/jedi/third_party/typeshed/stdlib/2and3/xml/etree. So I ran the command `cd /usr/lib/python3/dist-packages/jedi/third_party/typeshed/stdlib/2and3/xml/etree` to access it. Then I ran the command ls -a to view all the files including the hidden ones. This showed the following files:
```
.  ..  DISPATCH  ElementInclude.pyi  ElementPath.pyi  ElementTree.pyi  __init__.pyi  cElementTree.pyi
```
I ran the command cat  DISPATCH to get the next clue. The next clue was in: /usr/share/thumbnailers. It was a hidden file and the filename started with a '.' character. I ran the command ls -a to view all the files including the hidden ones. This showed the following files: .  ..  .WHISPER  librsvg.thumbnailer
Since .WHISPER started with a '.', I ran the command cat .WHISPER which showed the following: 
```The next clue is in: /opt/linux/linux-5.4/include/config/need/per/cpu/page/first```. The clue was trapped so I firsd ran the command cd / then `ls /opt/linux/linux-5.4/include/config/need/per/cpu/page/first`
to view the files. The files were : SPOILER-TRAPPED  chunk.h. So I ran the command `cat /opt/linux/linux-5.4/include/config/need/per/cpu/page/first/SPOILER-TRAPPED` to get the clue in SPOILER-TRAPPED. The next clue was in  /usr/local/lib/python3.8/dist-packages/angr/analyses. I ran the command ls /usr/local/lib/python3.8/dist-packages/angr/analyses to view the files. There was a file SNIPPET-TRAPPED which seemed to have the next clue. I ran `cat /usr/local/lib/python3.8/dist-packages/angr/analyses/SNIPPET-TRAPPED` to get the next clue. The next clue was in /usr/lib/x86_64-linux-gnu/blas. It was a delayed clue so I ran `cd /usr/lib/x86_64-linux-gnu/blas` and `ls -a` to access the files in it. Then I ran the command `cat  NUGGET` to get the next clue. The next clue was a hidden file in /usr/local/lib/python3.8/dist-packages/angr/angrdb/serializers so I ran the command `cd /usr/local/lib/python3.8/dist-packages/angr/angrdb/serializers` followed by `ls -a` to view all files. Then I ran `cat .INFO` to get then next clue. The next clue was again a hidden file in /opt/linux/linux-5.4/arch/arm/mach-omap1. So I ran the command `cd /opt/linux/linux-5.4/arch/arm/mach-omap1`. I ran the command `cat .CLUE` to get the next clue. The next clue was a delayed file, which had to be entered by 'cd', in /opt/linux/linux-5.4/arch/openrisc/mm. I ran the command  `cd  /opt/linux/linux-5.4/arch/openrisc/mm` folllowed by ` ls -a`. At last, I ran the command `cat TRACE` and received the flag.

Flag link: pwn.college{ADUSgBVviQAGM7ndpn7WZN0pa9H.dljM4QDL1YTN0czW}
## Challenge 10: Making Directories
This challenge required us to create a /tmp/pwn directory and make a college file in it. I ran the command cd /tmp to get into the temp directory. Then I ran the command `mkdir /tmp/pwn` to create /tmp/pwn directory. Then in order to make a college file I ran the command `touch /tmp/pwn/college`. Finally the /challenge/run command yielded the flag.

Flag link: pwn.college{EgCyoTgLPNkS5KKzS4DfV0jCHuv.dFzM4QDL1YTN0czW}
## Challenge 11: Finding Flags
I started with the command  'find / -name flag' to search the whole filesystem for flag file. This resulted in a long list of directories and most of them denied permission to access them. Only the following directories had files named flag in them: 
```
/usr/local/share/radare2/5.9.5/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/racket/pkgs/racket-index/scribblings/main/flag
/home/hacker/flag 
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
```
Then I tried catting every path to find the flag. Finally, the following step yielded the flag:
```
hacker@commands~finding-files:~$  cat /usr/share/racket/pkgs/racket-index/scribblings/main/flag
pwn.college{0kuqioFBsjAp5Tjs9aWaqLUGI-j.dJzM4QDL1YTN0czW}hacker@commands~finding-files:~$
```

Flag link: pwn.college{0kuqioFBsjAp5Tjs9aWaqLUGI-j.dJzM4QDL1YTN0czW}
## Challenge 12: Linking Files
I started with the command `ln -s /flag /home/hacker/not-the-flag` to create a symbolic link that points to the flag. Then I typed /challenge/catflag wich gave the following prompt:
```
About to read out the /home/hacker/not-the-flag file!
```
as it was read from the symlink instead of the original file. Then the flag was given.

Flag link: pwn.college{owi-HXf8EPOOG7xRQjKRISPiirT.dlTM1UDL1YTN0czW}
