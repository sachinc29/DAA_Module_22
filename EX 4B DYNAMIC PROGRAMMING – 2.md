# EX 4B DYNAMIC PROGRAMMING – 2
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm:  

1. Define function `LCS(X, Y, m, n)` to find the longest common substring between `X` and `Y`.  
2. Initialize `maxLength = 0` and `endingIndex = m` to track the length and end position of the LCS.  
3. Create a 2D list `lookup` of size `(m+1) x (n+1)` initialized with zeros.  
4. Loop over `i` from 1 to `m` and `j` from 1 to `n`.  
5. If characters `X[i-1] == Y[j-1]`, set `lookup[i][j] = lookup[i-1][j-1] + 1`.  
6. If the new value `lookup[i][j]` is greater than `maxLength`, update `maxLength` and `endingIndex`.  
7. After filling the table, return the substring `X[endingIndex - maxLength : endingIndex]`.  
8. Read input strings `X` and `Y`.  
9. Compute their lengths `m` and `n`.  
10. Call `LCS(X, Y, m, n)` and print the result as the longest common substring.  

## Program:
```
/*
Program to implement the longest common substring problem.
Developed by: Sachin C
Register Number: 212222230125
*/
```
```python
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```

## Output:

![image](https://github.com/user-attachments/assets/bc522377-bf3f-4a98-9460-2fb660a9947d)


## Result:
Thus the program was executed successfully for finding the longest common substring .
