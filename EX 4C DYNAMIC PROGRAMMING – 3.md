# EX 4C DYNAMIC PROGRAMMING – 3
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm:  

1. Initialize a 2D list `dp[1001][1001]` with all values set to -1 for memoization.  
2. Define function `lps(s1, s2, n1, n2)` to compute the longest common subsequence between `s1` and `s2`.  
3. If either `n1` or `n2` is 0, return 0 (base case for recursion).  
4. If `dp[n1][n2]` is already computed, return its value to avoid recomputation.  
5. If `s1[n1 - 1] == s2[n2 - 1]`, set `dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)` and return it.  
6. Else, set `dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))` and return it.  
7. Take user input as `seq` and assign `n = len(seq)`.  
8. Create a reversed version of `seq` as `s2 = seq[::-1]`.  
9. Call `lps(s2, seq, n, n)` to compute the LPS length.  
10. Print the result as the length of the Longest Palindromic Subsequence.  

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it.
Developed by: Sachin C
Register Number: 212222230125
*/
```
```python
dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))
```

## Output:

![image](https://github.com/user-attachments/assets/ae23f211-8f91-4a3c-a183-9c5b5a52fc77)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
