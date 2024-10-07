# Module 5:File_Globbing 
## Challenge 1: Matching with *
This challenge required us to change our directory to /challenge, but use globbing to keep the argument we pass to cd to at most four characters.
So, I ran the command `cd /ch*` as ch* would match the pattern of challenge. Then I ran the command `/challenge/run` to retrieve the flag.

Flag link: pwn.college{QFVaK-36p2ba-7DZIrE0KjVnvh2.dFjM4QDL1YTN0czW}
## Challenge 2: Matching with ?
This task required us to use ? character for globbing. The shell treats ? as a single character wildcard. So I ran the command `cd /?ha??enge` as c and l had to be exchanged with ? to pass as an argument to cd. Then I ran the command `/challenge/run` to retrieve the flag.

Flag link: pwn.college{8V_9sf3gRr82CeRxdjGtR5wrExG.dJjM4QDL1YTN0czW}
## Challenge 3: Matching with []
This challenge required us to use [] as a wildcard for some subset of potential characters. First, I changed my working directory to /challenge/files by the command `cd /challenge/files`. Then I ran the command `/challenge/run file_[bash]` which yielded the flag. Here I used file_[bash] as a single argument that bracket-globs into file_b, file_a, file_s, and file_h.

Flag link: pwn.college{E0NO-uKYQHyillcXhIQ7JhF3bIu.dNjM4QDL1YTN0czW}

## Challenge 4: Matching paths with []
This challenge required us to start from our home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files. Since, I was already in the home directory, I ran the command `/challenge/run /challenge/files/file_[b,a,s,h]` to get the flag. Here, I ran the command /challenge/run with the absolute path of the bracket-globbed files as the argument.

Flag link: pwn.college{wVkZKqPH9RYL7c2rM24biIM9m7E.dRjM4QDL1YTN0czW}
## Challenge 5: Mixing Globs
This challenge required us to write a 6 characters or less glob that will match the files "challenging", "educational", and "pwning". I started by changing the directory by running the command `cd /challenge/files`. Then I ran the command `/challenge/run [cep]*`. Here, I passed [cep]* as the arqument as the name of the files "challenging", "educational", and "pwning" contain one of the letters from [cep] and * is to match the pattern with the available files.

Flag link: pwn.college{c73O2m42A7xX7aOD17tgJsEpP4r.dVjM4QDL1YTN0czW}
## Challenge 6: exclusionary Globbing
In this challenge we had to filter out files in a glob by inverting the glob. I started by changing the directory by running the command `cd /challenge/files`. Then I ran the command `/challenge/run [!pwn]*` to filter out any file sarting with p, w or n and this yielded the flag.

Flag link: pwn.college{I1IGxCs1UHBQHvCtxHqqFYCG4js.dZjM4QDL1YTN0czW}
