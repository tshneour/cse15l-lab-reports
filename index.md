## Lab Report 1
# Step 1 - Installing VScode
For the first step, I set up VScode. Since it was already pre-installed on the basement computers,
I could just pull it up. If you don't already have VScode, download it here [VScode](https://code.visualstudio.com/). From there, I pulled up a git bash terminal and got started. 

![image](https://user-images.githubusercontent.com/122496719/211948544-595629f8-ce0d-4023-976a-665ed0e7eda5.png)

# Step 2 - Remotely Connecting
In the terminal, I typed in `ssh cs15lwi23zz@ieng6.ucsd.edu` (replacing zz with my account-specific letters) which allows me to connect remotely to another computer (in this case my course computer). This prompted me to verify my password and connection authenticity.
As seen below, I succeeded in signing in (with some connection statistics on the side).

![image](https://user-images.githubusercontent.com/122496719/212522335-2dbb7c5e-6867-4f4d-a303-5d0fe8e6913f.png)


# Step 3 - Testing Out Commands
After signing in, I messed around with some commands (most notably the `ls` command). With the `ls` command I was able to list folders in the current directory and even hidden files with the `-lat` argument.
As seen however, I was denied from using this to peer into other users' folders.

![image](https://user-images.githubusercontent.com/122496719/212522489-0a5af1b4-386f-41ef-bcfe-40b13c90fbe7.png)

Something I learned after messing with the `-lat` argument is that you can see not just hidden files but all their related details like size, date and the user of those files. I suspect the `drwxr-sr-x` to the left of the perl5 file represents permissions where `r` represents "read" and `w` represents "write." After a quick Google search, apparently `s` represents the user and `x` represents "executable." This explains why I am not allowed to use the `ls` command on other user directories.
