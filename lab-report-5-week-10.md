# CSE15L WEEK10 LAB REPORT
## By Guanyu Zhu 

In the instruction, the code that we use to run the test is 

  ```diff student-mdparse/results.txt markdown-parse/results.txt ```
  
On my end, the code I run is 

  ```diff newmarkdownparse/markdown-parse/results.txt week10labreports/markdown-parse/results.txt```
  
The command ```diff``` will compare the contents of two txt file and then point out the differences. 
The ```results.txt``` file contains the results that the program runned. 

- Difference 1
- Text:
  ```[foo](/bar\* "ti\*tle")```
- ![image](Screen%20Shot%202022-03-12%20at%206.25.49%20PM.png)
- The file correpsond with this error is 
- ![image](Screen%20Shot%202022-03-12%20at%205.55.27%20PM.png)
- By using commonmark, this is the desire output
- ![image](Screen%20Shot%202022-03-12%20at%206.10.30%20PM.png)
- Potential lines that causes the bug
- ![image](Screen%20Shot%202022-03-12%20at%206.05.03%20PM.png)
- The program find the string, but affected by the space, leading to a empty return[]
- To fix the bug, the program should be able to identify the space inside the link and determine the part of string that contains the actual link.




- Difference 2
- Text:
  ```[link](\(foo\))```
- ![image](Screen%20Shot%202022-03-12%20at%206.29.04%20PM.png)
- The file correspond to the error is
- ![image](Screen%20Shot%202022-03-12%20at%206.30.53%20PM.png)
- By using commonmark, this is the desire output
- ![image](Screen%20Shot%202022-03-12%20at%206.33.03%20PM.png)
- Potential lines that causes the bug
- ![image](Screen%20Shot%202022-03-12%20at%206.35.30%20PM.png)
- The program on my repo has the issue with identifying the backslash\
- To fix the bug, the program should be able to identify nested parenthesis. A modified while loops might be able to solve this potential problem
