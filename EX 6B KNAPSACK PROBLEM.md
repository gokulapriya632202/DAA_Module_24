# EX 6B KNAPSACK PROBLEM
## DATE: 08/04/2025
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.
## Algorithm
1. Base case: If there are no items left or the capacity is 0, return 0.
2. Item exclusion: If the current item's weight is greater than the remaining capacity, skip it.
3. Item inclusion: Otherwise, choose between including the item or excluding it.
4. Recursive calls: Recursively solve the problem by either excluding or including the item.
5. Return maximum value: At each step, return the maximum value of including or excluding the current item.  

## Program:

### To implement the program for 0/1 knapsack problem.
### Developed by: GOKULA PRIYA P  
### Register Number: 212222040044
```
def knapSack(W, wt, val, n):
    K = [[0 for x in range(W + 1)] for x in range(n + 1)]
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                K[i][w] = 0
            elif wt[i-1] <= w:
                K[i][w] = max(val[i-1]+ K[i-1][w-wt[i-1]],K[i-1][w])
            else:
                K[i][w] = K[i-1][w]
 
    return K[n][W]

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```
## Output:
![Screenshot 2025-05-24 203126](https://github.com/user-attachments/assets/a553ec91-3b28-4df3-8cc6-d43d1e85ede4)

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
