## Lab Report 5

In this lab report, I will be showing a quicker way to do the lab competition from report 4 using bash scripting.

# Part 1 - Writing the Bash Script

Writing the bash script was pretty straightforward. For the most part, I'm able to reuse most of the commands that I used in lab report 4 (as seen below).
I will go into more detail on these commands in Part 2.

![image](https://user-images.githubusercontent.com/122496719/224612337-8d4f51fa-d9c1-4251-8b71-26290386d239.png)

The only problem I ran into is that I couldn't include the `ssh cs15lwi23aom@ieng6.ucsd.edu` command. The reason being that the commands after `ssh` won't run until 
I `exit` back to my local machine. From my understanding, this has something to do with administrator privileges. Frankly, it's a lot easier **not** to mess with 
that so I chose to run `scp ~/OneDrive/Desktop/Bruh\ Momentum/CSE15L/bruuh/typoFixer.sh  cs15lwi23aom@ieng6.ucsd.edu:~/` instead which copies the bash file over to 
my ieng6 account. Then, I manually typed in the `ssh` command to log in.

# Part 2 - Speedrunning The Competition

Here, I'll outline exactly what keys I pressed and what commands I ran (including the contents of the script).

# Part 2.1 - Moving Over The Bash File

![image](https://user-images.githubusercontent.com/122496719/224612391-7b6f4616-4ecf-4ba8-b6b2-0653be25a8ee.png)

*Keys pressed:* `<Ctrl-R> scp <enter>`
  
I used reverse search to run the `scp ~/OneDrive/Desktop/Bruh\ Momentum/CSE15L/bruuh/typoFixer.sh  cs15lwi23aom@ieng6.ucsd.edu:~/` command quickly. As seen, this 
copied my bash script over to my ieng6 account. 
  
# Part 2.2 - Logging In

![image](https://user-images.githubusercontent.com/122496719/224612421-c570a152-187e-4481-8159-b9ddece9be9c.png)
  
*Keys pressed:* `<Ctrl-R> ssh <enter>`
  
I used reverse search to run the `ssh cs15lwi23aom@ieng6.ucsd.edu` command. This logged me into my ieng6 account.
  
# Part 2.3 - Running The Bash Script
  
![image](https://user-images.githubusercontent.com/122496719/224612675-b145a352-13a8-403e-9a5d-21daf6e723f7.png)

*Keys pressed:* `<Ctrl-R> b <enter>`
  
I used reverse search to run the `bash typoFixer.sh` command. This ran the bash file, specifically the first few commands as seen below.

```
rm -rf lab7
git clone git@github.com:tshneour/lab7.git
cd lab7
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples.java
nano ListExamples.java
```

In the first line, the bash script removes the `lab7` folder (done for testing). The next line clones my fork of the `lab7` repository. Then it uses `cd` to move 
into the cloned directory. The `javac` and `java` commands run the tests (which fail as expected). Lastly, `nano ListExamples.java` opens up the `ListExamples.java` 
file for me to edit. The bash script pauses here until I exit out of the file.

# Part 2.4 - Editing The File

![image](https://user-images.githubusercontent.com/122496719/224611920-6aad2c47-1bd4-44d8-a52f-c8415c9e8178.png)

*Keys pressed:* `<Ctrl-W> <Alt-B> x1 <enter>, <right> <right> <backspace> 2, <Ctrl-O> <enter>, <Ctrl-X>`

Same as before, I used the `<Ctrl-W>` and `<Alt-B>` shortcuts to search for `x1` in reverse order. This brought me to `index1 += 1` at the end of the file which I 
changed into `index2 += 1` (after shifting places with the arrow keys). Then I used `<Ctrl-O>` to save changes and `<Ctrl-X>` to exit.

# Part 2.5 - Bash Script Completes

![image](https://user-images.githubusercontent.com/122496719/224613128-ac2b50b6-4fe2-4245-bdc7-5b39b5c15818.png)

As seen, the rest of the bash script completes. This reruns the tests (which pass this time) then pushes the changes to Github. Below are the commands that ran.

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
git add ListExamples.java
git commit -m "Fixed index typo"
git push
```

The `javac` and `java` commands recompile and run the tests again. The `git add` command tells Git what files I'm committing. Then `git commit -m "Fixed index
typo"` prepares those files to be sent to the repository. Lastly, the git push command sends those files to my forked repository and in this case, replaces
the old `ListExamples.java` file.

So, even though it's technically cheating, I was able to complete the competition in 3 commands and a few keypresses. Definitely **way** faster than before.
