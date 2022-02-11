# CSE15L WEEK6 LAB REPORT
## By Guanyu Zhu 

**Group Choose 3: Copy whole directories with ```scp -r```
![image](Screen%20Shot%202022-02-10%20at%2010.48.40%20PM.png)
- first we use ```pwd``` to check if we are in the directory we want to copy
---
![image](Screen%20Shot%202022-02-10%20at%2010.48.58%20PM.png)
- second we can use code ```scp -r . ieng6:markdown-parse-main-2``` to copy the entire directory to the server
- After we done, we can ssh to ieng6 and check if the file was copied correctly
---
![image](Screen%20Shot%202022-02-10%20at%2010.49.24%20PM.png)
- Use ```cd``` to access the folder and use ```ls``` to check the contents
---
![image](Screen%20Shot%202022-02-10%20at%2010.53.49%20PM.png)
- Lastly, we can use ```;``` to seperate the command so that we can run multiple command on single line
- Type in ```javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest```
- It can run the JUnit test for the file and show the result
