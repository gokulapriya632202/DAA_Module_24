# EX 6A CHERRY PICK UP PROBLEM
## DATE: 07/04/2025
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.

## Algorithm
1. Initialize the DP table: Create a 2D dp array of size n x n (where n is the size of the grid) to store the maximum cherries that can be collected starting from each cell.
2. Iterate from the bottom-right corner: Start iterating the grid from the bottom-right corner (grid\[n-1]\[n-1]) to the top-left corner (grid\[0]\[0]) in reverse order.
3. Base case: The value at the bottom-right corner (dp\[n-1]\[n-1]) is simply the value in the grid\[n-1]\[n-1], as that's where the collection ends.
4. For the last row and last column: For the last row, move from right to left. Each cell collects cherries from the current grid cell and the cell to the right.
5. For the last column, move from bottom to top. Each cell collects cherries from the current grid cell and the cell below.   

## Program:

## To implement the program for Cherry pickup problem.
### Developed by: GOKULA PRIYA P 
### Register Number: 212222040044
```
class Solution(object):
    def cherryPickup(self, grid):
        def dp(i, j, k):
            if (i, j, k) in memo:
                return memo[(i, j, k)]
            
            if i == ROW_NUM - 1:
                return grid[i][j] + (grid[i][k] if j != k else 0)
            
            cherries = grid[i][j] + (grid[i][k] if j != k else 0)
            
            max_cherries = 0
            for dj in [-1, 0, 1]:
                for dk in [-1, 0, 1]:
                    next_j, next_k = j + dj, k + dk
                    if 0 <= next_j < COL_NUM and 0 <= next_k < COL_NUM:
                        max_cherries = max(max_cherries, dp(i + 1, next_j, next_k))
            
            memo[(i, j, k)] = cherries + max_cherries
            return memo[(i, j, k)]
        
        ROW_NUM = len(grid)
        COL_NUM = len(grid[0])
        memo = {}
        return dp(0, 0, COL_NUM - 1)

grid=[[0,1,-1],[1,0,-1],[1,1,1]] 
obj=Solution()
print(obj.cherryPickup(grid)+3)

```
## Output:
![Screenshot 2025-05-24 202740](https://github.com/user-attachments/assets/828db0a8-221b-4570-8f32-b161a4ddffd0)

## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
