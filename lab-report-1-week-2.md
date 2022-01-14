# CSE15L WEEK2 LAB REPORT
## By Guanyu Zhu 
**STEP 1: Installing VScode**
- Go to https://code.visualstudio.com/
- Download the VScode version that fit your operating system
- Install VScode on your device

**STEP 2: Remote Connecting**
- Before we do the actual steps, we need to find our account first
  - Go to https://sdacs.ucsd.edu/~icc/index.php
  - Fill out the information and write down your persoanl account for this course
- Then, we can start to access server remotely on your local device
  - Open a new terminal in VScode (Ctrl or Command + `, or use the Terminal → New Terminal menu option)  
  - And then type in command
    ```
    $ ssh cs15lwi22zz@ieng6.ucsd.edu
    ```
  - Replace zz with your specific letters
  - After that, the authentification will appear and you should type "yes"
  - Now, you should have login your account successfully it should looks like this
  - ![image](https://github.com/g6zhu/cse15l-lab-reports/blob/main/Screen%20Shot%202022-01-13%20at%208.38.01%20PM.png)

**STEP 3: Run Some Commands**
- We can try some command on terminal
  - For example, we can try ```ls``` in a couple different variation
  - ```ls ```
  - ```ls -lat ```
  - ```ls -a ```
  - You should see something like this
  - ![image](https://github.com/g6zhu/cse15l-lab-reports/blob/main/Screen%20Shot%202022-01-13%20at%208.43.49%20PM.png)
  - You can also try ```cd ``` to access the folder
  - Finally, if you want to exit the account and back to your local terminal, you should type ```exit```

**STEP 4: Moving Files with scp**
- We can always move files from local to server by using command ```scp```
- Let's try
  - Create a local file named WhereAmI.java
  - And put the following contents into the lines
```
    class WhereAmI {
        public static void main(String[] args) {
           System.out.println(System.getProperty("os.name"));
           System.out.println(System.getProperty("user.name"));
           System.out.println(System.getProperty("user.home"));
           System.out.println(System.getProperty("user.dir"));
           }
    }
```
- Compile this java file locally using ```javac``` and ```javac```
- After that, type the following command into your terminal
- ```scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/```
- Replace 'zz' with your specific characters, Login with your password
- Login into your account again, and type ```ls```, you should see your file up there
- ![image](https://github.com/g6zhu/cse15l-lab-reports/blob/main/Screen%20Shot%202022-01-13%20at%209.00.29%20PM.png)

**STEP 5: Setting an SSH Key**
- Entering key everytime is time consuming and annoying, here is a way to skip tha step
- We will create a SSH key so that it build a 1-to-1 connect to your laptop and server
- To do this, we need to first exit the server and back to local terminal
  - On client side, type in command ```ssh-keygen```
  - You should see some thing like this
  ```
  # Generating public/private rsa key pair.
    Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /Users/joe/.ssh/id_rsa.
    Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
    The key's randomart image is:
    +---[RSA 3072]----+
    |                 |
    |       . . + .   |
    |      . . B o .  |
    |     . . B * +.. |
    |      o S = *.B. |
    |       = = O.*.*+|
    |        + * *.BE+|
    |           +.+.o |
    |             ..  |
    +----[SHA256]-----+
     ``` 
  - Since I alreay done this, I do not wish to create a file again, however, it should be something like this
  - ![image](https://github.com/g6zhu/cse15l-lab-reports/blob/main/Screen%20Shot%202022-01-13%20at%209.21.55%20PM.png)
  - Be sure to save the file on your appointed location   
  - After that, you can login to your account using ```ssh```
  - We just created two key files, one public and one private
  - Follow the instruction below, and you should change your directory for the file, search for your directory on local first
  ```
  $ mkdir .ssh
  $ <logout>
  # back on client
  $ scp /Users/joe/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
  # You use your username and the path you saw in the command above
  ```
  - You can now login with your account, no key should be required now

**STEP 6: Optimizing Remote Running**
- There are many ways you can use the command to get a easy access to the server
- Some command is very useful
- For example, you can do the command ```ssh cs15lwi22@ieng6.ucsd.edu "ls"```
- It will list the file you have without actually login your account
- ![image](https://github.com/g6zhu/cse15l-lab-reports/blob/main/Screen%20Shot%202022-01-13%20at%209.17.07%20PM.png)
