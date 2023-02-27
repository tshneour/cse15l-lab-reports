## Lab Report 4

In this lab report, I will be covering my approach to the lab competition. For each step after the timer, I will be explaining what commands I used.

# Step 4 - Logging In

![image](https://user-images.githubusercontent.com/122496719/221447664-ff40086a-1da7-405a-9641-5a531f5849ca.png)

*Keys pressed:* `<Ctrl-R> ssh <enter>`

The `ssh cs15lwi23aom@ieng6.ucsd.edu` command was in my search history so I was able to use reverse search to use it. This logged me into my ieng6 account.

# Step 5 - Cloning the Fork

![image](https://user-images.githubusercontent.com/122496719/221448814-7fcceb58-5f2c-4486-8715-97b0665e212f.png)

*Keys pressed:* `<Ctrl-R> git c <enter>`

The `git clone git@github.com:tshneour/lab7.git` command was in my search history so I reverse searched it. This cloned my forked repository using my `ssh` key to clone instead of the `https` link.

# Step 6 - Run the Tests

![image](https://user-images.githubusercontent.com/122496719/221449791-41fa8539-5d51-4037-a4a0-bd61249d1a51.png)

*Keys pressed:* `cd <space> l <tab> <enter>, <Ctrl-R> javac <enter>, <Ctrl-R> java <space> <enter>`

I used `<tab>` to autocomplete the `cd` command into `cd lab7/` which let me get into the cloned directory. From there, I used reverse search to access `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` from my search history. The `javac` command compiled the java files then the `java` command ran the tests.

# Step 7 - Fix the Code File

![image](https://user-images.githubusercontent.com/122496719/221451814-8019f8a3-1f72-43f3-926d-0ee39ae97fab.png)
![image](https://user-images.githubusercontent.com/122496719/221451961-58103654-e740-4cf3-ba38-6c39537240d7.png)


*Keys pressed:* `<Ctrl-R> na <enter>, <Ctrl-W> <Alt-B> x1 <enter>, <right> <right> <backspace> 2, <Ctrl-O> <enter>, <Ctrl-X>`

First, I used reverse search to access the `nano ListExamples.java` command which opened the `ListExamples.java` file in the nano editor. From there, I used the `<Ctrl-W>` and `<Alt-B>` shortcuts to search for `1` in reverse order. This brought me to `index1 += 1` at the end of the file which I navigated to and then edited into `index2 += 1`. Then I used `<Ctrl-O>` to save changes and `<Ctrl-X>` to exit.

# Step 8 - Run the Tests Again

![image](https://user-images.githubusercontent.com/122496719/221452225-983a0983-cc8b-4582-b390-a8df8fd7c318.png)

*Keys pressed:* `<Ctrl-R> javac <enter>, <Ctrl-R> java <space> <enter>`

I used reverse search to access `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` from my search history. The `javac` command compiled the java files then the `java` command ran the tests which all passed this time.

# Step 9 - Push the Changes to Github

![image](https://user-images.githubusercontent.com/122496719/221452607-98cabfb2-a1be-40a1-9c84-858297cf3c37.png)

*Keys pressed:* `<Ctrl-R> git a <enter>, <Ctrl-R> git co <enter>, <Ctrl-R> git p <enter>`

I used reverse search to access the `git add ListExamples.java`, `git commit -m "test"`, and `git push origin main` commands. The `git add` command told Git what files I want to commit that I have changed. Then `git commit -m "test"` told Git to prepare those files to be sent to the repository with the commit message `test`. Lastly, the `git push` command sent those files to the forked repository and replaced the old files with them. 
