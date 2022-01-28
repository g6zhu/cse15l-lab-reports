# CSE15L WEEK4 LAB REPORT
## By Guanyu Zhu 

**Change 1:
- ![image](Screen%20Shot%202022-01-28%20at%202.34.03%20PM.png)
- The first big major change is aim to resolve the problem of multi brackets
- Without changes, the result will looks like following, which is incorrect
- -![image]()
- ```[a link!]((https://something.com))
     [another link!](some-page.html)```
- The multiple brackets appear on the above input is caused by the wrong counting of brackets
- The output suppose to no include the brackets. However, the wrong output include a open brackets
- To fix such problem, we only need to count the number of open and closed brackets so to match it

**Change 2:
- ![image](Screen%20Shot%202022-01-28%20at%202.53.30%20PM.png)
- The second major change is aim to resolve the empty line appear on the top of input
- The empty line will causes the a infinite loop
- ![image](Screen%20Shot%202022-01-28%20at%203.05.10%20PM.png)
- ```
  
  [](a link on the first line)
  [```
- The empty line appear on top of the links will causes the while loop does not detect any thing
- Thus result in a infinite loop
- To fix the problem, we can resolve it by writing the method in order to detect whether a new line exist

**Change 3;
- The thrid change is we avoid the problem of indexOutOfBoundException
- ![image](Screen%20Shot%202022-01-28%20at%203.30.19%20PM.png)
- ```# title

    []

    more text here
  ```
- If we do not have and left or right brackets exist. Then the program will not be able to count end point
- The default return will be -1 by java
- However, -1 is not a valid index
- To fix this problem, we can simply continue the process so to keep the entire program running
