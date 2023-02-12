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


## Lab Report 2
# Part 1 - The StringServer Class

![image](https://user-images.githubusercontent.com/122496719/215647371-a483ea32-0636-482f-bb80-5f3ad6e0bc93.png)

Above is my code for my implementation of the StringServer class. I have reused the Server class from week 2 in order to support setting up a server. Inside is another class named Handler that "handles" the `/add-message` request.

![image](https://user-images.githubusercontent.com/122496719/215648500-7f9f0ac8-3857-43eb-91eb-213bd8364f1e.png)

In the above screenshot, I am using the handleRequest method in order to add a message. This method takes in a parameter `url` of type `URI`. The main value used by the class is `String message` which is updated to hold "easy" with this `/add-message` request.

![image](https://user-images.githubusercontent.com/122496719/215653265-16216a1e-28e1-40e7-8b21-95d650f14b97.png)

In this instance of `/add-message`, I am still using the handleRequest method where it takes in a `URI`. In this case, the URI is `http://localhost:8080/add-message?s=dub`. This time, `message` is concatenated with a newline (\n) and the new message after `=` which is `dub`.

# Part 2 - ReverseInPlace Bug
```
@Test 
public void testReverseInPlaceOddArray() {
    int[] input1 = { 3, 5, 7 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 7, 5, 3 }, input1);
}
```

```  
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```  

  ![image](https://user-images.githubusercontent.com/122496719/215655381-6f0d83c7-5564-46e1-b052-549e29b8147e.png)

```
// Changes the input array to be in reversed order
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```  

```  
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
}
```  

  By creating a `temp` variable and reducing the length of the for loop by half, the after code runs properly. In the before-code, the for loop would end up creating a palindrome since the first half of the input array would be replaced by the second half. Since the code has no way to access the prior values of the first half, `temp` is used in the after-code to set the opposite side value to the original value. The `arr.length/2` accounts for the for loop modifying both ends of the array.
  
# Part 3 - What I Learned

Something I learned from week 3 was how to properly approach testing a program. Before, I would try random inputs whenever testing a program and seeing if anything was out of place. However, designing and using tests with JUnit taught me how much more efficient it was to systematically write and run tests. This is because I could break down bugs into failure-inducing inputs and symptoms. Plus, since I would know what that test was testing for, I would have an idea of where to look for the bug.

## Lab Report 3

