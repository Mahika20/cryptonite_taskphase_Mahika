# Module 2
## Challenge 1: The Root
This challenge required us to invoke the pwn program using its absolute path in terminal. I typed /pwn and pressed the enter key which yielded the flag.
Flag link: pwn.college{Q-pQcxVn5CO3cu7naqhK0Se9khn.dhzN5QDL1YTN0czW}
## Challenge 2: Program and Absolute Paths
This challenge required us to invoke the run challenge program which is in the challenge directory, using its absolute path. Here, the root directory is challenge in which run resides. So, I invoked it using the command /challenge/run and pressed the enter key which yielded the flag.
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

