# EX 4A DYNAMIC PROGRAMMING - 1
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm:

1. Define function `lcs(str1, str2)` to find the length of the Longest Common Subsequence.  
2. Get the lengths `m` and `n` of the two input strings.  
3. Create a 2D list `matrix` of size `(m+1) x (n+1)` initialized with zeros.  
4. Loop through all indices `i` from 0 to `m` and `j` from 0 to `n`.  
5. If `i == 0` or `j == 0`, set `matrix[i][j] = 0` (base case of empty substring).  
6. If characters `str1[i-1] == str2[j-1]`, set `matrix[i][j] = 1 + matrix[i-1][j-1]`.  
7. Otherwise, set `matrix[i][j] = max(matrix[i-1][j], matrix[i][j-1])`.  
8. After filling the matrix, return the value at `matrix[m][n]` which is the LCS length.  
9. Read two input strings `str1` and `str2` from the user.  
10. Call the `lcs` function and store the result in `lcs_length`.  
11. Print the LCS length using formatted output.  

## Program:
```
Program to implement the longest common subsequence using Dynamic Programming.
Developed by: Sachin C
Register Number: 212222230125
```
```python
def lcs(str1 , str2):
    m = len(str1)
    n = len(str2)
    matrix = [[0]*(n+1) for i in range(m+1)] 
    for i in range(m+1):
        for j in range(n+1):
            if i==0 or j==0:
                matrix[i][j] = 0
            elif str1[i-1] == str2[j-1]:
                matrix[i][j] = 1 + matrix[i-1][j-1]
            else:
                matrix[i][j] = max(matrix[i-1][j] , matrix[i][j-1])
    return matrix[-1][-1]
str1 = input()
str2 = input()
lcs_length = lcs(str1, str2)
print("Length of LCS is : {}".format(lcs_length))
```

## Output:

![image](https://github.com/user-attachments/assets/facbdfbb-b37c-4460-9f84-e37c55b6e251)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
