## Lab Report 5

In this lab report, I will be showing a quicker way to do the lab competition from report 4 using bash scripting.

# Part 1 - Writing the Bash Script

Writing the bash script was pretty straightforward. For the most part, I'm able to reuse most of the commands that I showed in lab report 4 (as seen below).

![image](https://user-images.githubusercontent.com/122496719/224607760-629c7594-e244-412a-a42d-b35572f1ee13.png)

The only problem I ran into is that I couldn't include the `ssh cs15lwi23aom@ieng6.ucsd.edu` command. The reason being that the commands after `ssh` won't run until I
`exit` back to my local machine. From my understanding, this has something to do with administrator privileges. Frankly, it's a lot easier **not** to mess with that so
I chose to run `scp ~/OneDrive/Desktop/Bruh\ Momentum/CSE15L/bruuh/typoFixer.sh  cs15lwi23aom@ieng6.ucsd.edu:~/` manually which copies the bash file over to my ieng6 account.

# Part 2 - Speedrunning The Competition

Here, I'll outline exactly what keys I pressed and what commands I'm running (including the contents of the script).

# Part 2.1 - Moving Over The Bash File

![image](https://user-images.githubusercontent.com/122496719/224609513-f4531950-6e04-4c0a-89b6-1af3c6e8dd10.png)

*Keys pressed:* <Ctrl-R> scp <enter>
  
I used reverse search to run the `scp ~/OneDrive/Desktop/Bruh\ Momentum/CSE15L/bruuh/typoFixer.sh  cs15lwi23aom@ieng6.ucsd.edu:~/` command quickly. As seen, this copied my
bash script over to my ieng6 account. 
  
# Part 2.2 - Logging In
  
*Keys pressed:* <Ctrl-R> ssh <enter>
  
I used reverse search to run the `ssh cs15lwi23aom@ieng6.ucsd.edu` command. This logged me into my ieng6 account.
  
# Part 2.3 - Running The Bash Script
  
![image](https://user-images.githubusercontent.com/122496719/224610364-dbc54487-5c2d-4267-8afc-135b1b99e8ba.png)

*Keys pressed:* <Ctrl-R> b <enter>
  
I used reverse search to run the `scp ~/OneDrive/Desktop/Bruh\ Momentum/CSE15L/bruuh/typoFixer.sh  cs15lwi23aom@ieng6.ucsd.edu:~/` quickly. As seen, this copied my
bash script over to my ieng6 account. 
