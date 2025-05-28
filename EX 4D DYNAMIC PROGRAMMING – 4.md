# EX 4D DYNAMIC PROGRAMMING – 4
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm  

1. Define a recursive function `LD(s, t)` to calculate the minimum edit distance between strings `s` and `t`.  
2. If string `s` is empty, return the length of `t` (insert all characters of `t`).  
3. If string `t` is empty, return the length of `s` (delete all characters of `s`).  
4. If the last characters of `s` and `t` are the same, set `cost = 0`, else `cost = 1`.  
5. Recursively calculate the minimum of three options:  
   - Insert operation: `LD(s, t[:-1]) + 1`  
   - Delete operation: `LD(s[:-1], t) + 1`  
   - Replace/match operation: `LD(s[:-1], t[:-1]) + cost`  
6. Return the minimum of the three computed values.  
7. Take input strings `str1` and `str2` from the user.  
8. Print the computed edit distance between `str1` and `str2` using the `LD` function.  

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method.
Developed by: Sachin C
Register Number: 212222230125
*/
```
```python
def LD(s, t):
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))
```
## Output:

![image](https://github.com/user-attachments/assets/f24c041c-2949-47c1-b2f6-294db6b9a0b4)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
