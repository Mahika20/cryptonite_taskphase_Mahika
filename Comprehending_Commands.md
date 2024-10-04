# Module: 3
## Challenge 1: Cat not the pet but the command
In this challenge, I had to use the cat command to read the flag in the home directory. Since I was already in the home directory, I ran the command cat flag and received the flag.
Flag link: pwn.college{siugmP07oFB48BuaRkyA36dZhj6.dFzN1QDL1YTN0czW}
## Challenge 2: Catting absolute paths
For this challenge I used the command cat /flag to read the flag with cat at its absolute path /flag.
Flag link: pwn.college{s6b4NWL7xNvwSPTA4Wu5FLObnls.dlTM5QDL1YTN0czW}
## Challenge 3: More catting practice
This challenge required us to retrieve the flag, hidden in a different directory, by the absolute path. The absolute path of the file was provided in the instructions in terminal. I used the command 
'''cat /lib/x86_64-linux-gnu/libcanberra-0.30/flag''' 
to retrieve the flag.
Flag link: pwn.college{ohVn40PHnaHJlh3OAoi2RACmSKX.dBjM5QDL1YTN0czW}
## Challenge 4: Grepping for a needle in a haystack

Flag link: pwn.college{YTpYgDDgWmK0YmZzIcRTyHWbTuh.ddTM4QDL1YTN0czW}
## Challenge 5: Listing files

Flag link: pwn.college{kWsB9aIEuaOLmi8HDOhkXkqhQL7.dhjM4QDL1YTN0czW}
## Challenge 6:  Touching Files

Flag link: pwn.college{sx7Cdb_dkojRsuBDZmqXoP3I5o0.dBzM4QDL1YTN0czW}
## Challenge 7: Removing Files

Flag link: pwn.college{w9CmldOpcA3hxh0z1gKtaZjLwdg.dZTOwUDL1YTN0czW}
## Challenge 8: Hidden files
This challenge required us to find the hidden flag file in /. I ran the command cd / to access / directory. In order to view all the files, including the hidden ones, I ran the command ls ~a. There I found the dot-prepended flag file -> /.flag-19271559011509. Then to receive the flag, I ran the command 
'''grep pwn.college /.flag-19271559011509'''
Flag link: pwn.college{YY6mK3In_zfAUYo_g3ytI9WPH9g.dBTN4QDL1YTN0czW}
## Challenge 9: An Epic Filesystem Quest
This task required us to find the flag by following a series of clues. I first got into the / directory using cd / and then enetered the command ls to view the files. The following files were shown: 
'''EVIDENCE  challenge  flag  lib32   media  opt   run   sys  var
bin       dev        home  lib64   mnt    proc  sbin  tmp
boot      etc        lib   libx32  nix    root  srv   usr'''
Then I ran the command cat EVIDENCE as it lloked like a hint and got the clue. The next clue was in: /usr/lib/python3/dist-packages/jedi/third_party/typeshed/stdlib/2and3/xml/etree. So I ran the command cd /usr/lib/python3/dist-packages/jedi/third_party/typeshed/stdlib/2and3/xml/etree to access it. Then I ran the command ls -a to view all the files including the hidden ones. This showed the following files:
'''.  ..  DISPATCH  ElementInclude.pyi  ElementPath.pyi  ElementTree.pyi  __init__.pyi  cElementTree.pyi'''
I ran the command cat  DISPATCH to get the next clue. The next clue was in: /usr/share/thumbnailers. It was a hidden file and the filename started with a '.' character. I ran the command ls -a to view all the files including the hidden ones. This showed the following files: .  ..  .WHISPER  librsvg.thumbnailer
Since .WHISPER started with a '.', I ran the command cat .WHISPER which showed the following: 
'''The next clue is in: /opt/linux/linux-5.4/include/config/need/per/cpu/page/first'''. The clue was trapped so I firsd ran the command cd / then 'ls /opt/linux/linux-5.4/include/config/need/per/cpu/page/first'
to view the files. The files were : SPOILER-TRAPPED  chunk.h. So I ran the command 'cat /opt/linux/linux-5.4/include/config/need/per/cpu/page/first/SPOILER-TRAPPED' to get the clue in SPOILER-TRAPPED. The next clue was in  /usr/local/lib/python3.8/dist-packages/angr/analyses. I ran the command ls /usr/local/lib/python3.8/dist-packages/angr/analyses to view the files. There was a file SNIPPET-TRAPPED which seemed to have the next clue. I ran 'cat /usr/local/lib/python3.8/dist-packages/angr/analyses/SNIPPET-TRAPPED' to get the next clue. The next clue was in /usr/lib/x86_64-linux-gnu/blas. It was a delayed clue so I ran 'cd /usr/lib/x86_64-linux-gnu/blas' and 'ls -a' to access the files in it. Then I ran the command 'cat  NUGGET' to get the next clue. The next clue was a hidden file in /usr/local/lib/python3.8/dist-packages/angr/angrdb/serializers so I ran the command 'cd /usr/local/lib/python3.8/dist-packages/angr/angrdb/serializers' followed by 'ls -a' to view all files. Then I ran cat .INFO to get then next clue. The next clue was again a hidden file in /opt/linux/linux-5.4/arch/arm/mach-omap1. So I ran the command 'cd /opt/linux/linux-5.4/arch/arm/mach-omap1'. I ran the command 'cat .CLUE' to get the next clue. The next clue was a delayed file, which had to be enetered by 'cd', in /opt/linux/linux-5.4/arch/openrisc/mm. I ran the command  'cd  /opt/linux/linux-5.4/arch/openrisc/mm' folllowed by  ls -a. At last, I ran the command cat TRACE and received the flag.
Flag link: pwn.college{ADUSgBVviQAGM7ndpn7WZN0pa9H.dljM4QDL1YTN0czW}
## Challenge 10:

Flag link:
## Challenge 11:

Flag link:
## Challenge 12: 

Flag link:
