# Module 2: Pondering Paths
## Challenge 1: The Root
This challenge required us to invoke the pwn program using its absolute path in terminal. I ran the command `/pwn` which yielded the flag.

Flag link: pwn.college{Q-pQcxVn5CO3cu7naqhK0Se9khn.dhzN5QDL1YTN0czW}
## Challenge 2: Program and Absolute Paths
This challenge required us to invoke the run challenge program which is in the challenge directory, using its absolute path. Here, the root directory is challenge in which run resides. So, I invoked it using the command `/challenge/run` which yielded the flag.

Flag link: pwn.college{o6Kd9Hu1oErpM1lTiRu0t89lgyt.dVDN1QDL1YTN0czW}
## Challenge 3: Position thy self
The challenge required us to execute the /challenge/run program from a specific path. Initially, I ran the program cd /challenge to access the challenge directory. Then I ran the /challenge/run program to check the specific path. It resulted in the following prompt: 
'''
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
Please use the `cd` utility to change directory appropriately.
'''
The specific directory path was mentioned in the above block which is /var/lib/apt/lists. I changed the directory using cd with this path and then invoked /challenge/run which yielded the flag.

Flag link: pwn.college{cftv4x04OHWkQ-tSQzQA2HkCOzS.dZDN1QDL1YTN0czW}
## Challenge 4: Position elsewhere
This challenge required us to execute the /challenge/run program from a specific path. I first ran the command `/challenge/run ` which gave the following prompt:
```
Incorrect...
You are not currently in the /var/lib/apt/lists directory.
```
So, I ran the command `cd /var/lib/apt/lists` to change the directory and then ran the command `/challenge/run`. This step yielded the flag.

Flag link: pwn.college{8SMkwHVf_qbCcQssdYRUzB0tq64.ddDN1QDL1YTN0czW}
## Challenge 5: Position yet elsewhere
This challenge again required us to execute the /challenge/run program from a specific path. So, I ran the command `/challenge/run` which gave the following prompt:
```
Incorrect...
You are not currently in the /sys/kernel directory.
Please use the `cd` utility to change directory appropriately.
```
I then changed the directory by the command ` cd /sys/kernel` and again ran the command `/challenge/run` which yielded the flag.

Flag link: pwn.college{YN_MRnEi70FtAGJhPz7nigVb7Ev.dhDN1QDL1YTN0czW}
## Challenge 6: Implicit relative paths, from /
The challenge required us to run the command /challenge/run using a relative path while having a current working directory of /. I started by using the cd command with / to access the / directory. The current working directory was /. So the relative path to the file became challenge/run. I ran this path and received the flag.

Flag link: pwn.college{Y84U-pQ87XxMWVN63uTmUC-U1YL.dlDN1QDL1YTN0czW}
## Challenge 7: Explicit relative paths, from /
This challenge required us to invoke /challenge/run using . in the relative path. I ran the command `cd /` to access the / directory then ran `./challenge/run` which yielded the flag.

Flag link: pwn.college{oXNx3Bu3zsaSXVjv88PPy9dOY7P.dBTN1QDL1YTN0czW}
## Challenge 8: Implicit relative paths
For this challenge I ran the command cd /challenge to access the challenge directory. I used the relative path `./run` to launch run from the challenges directory. This step yielded the flag.

Flag link: pwn.college{wUhIjoP8-VmfEElN6AX2ZnPHC5C.dFTN1QDL1YTN0czW}
## Challenge 9: Home sweet home
For this challenge I ran the command `cd /challenge` to access the challenge directory. Then I ran the command `/challenge/run ~/h` where ~/h is the argument in which the copy of the flag was to be stored. This resulted in the following prompt:
```
Writing the file to /home/hacker/h!
... and reading it back to you:
```
Flag link: pwn.college{cTFAUt7a6W4n1UdiwkxrU821V51.dNzM4QDL1YTN0czW}


