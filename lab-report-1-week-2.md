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
  -  

**STEP 6: Optimizing Remote Running**
