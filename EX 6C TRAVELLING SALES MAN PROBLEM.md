# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE: 09/04/2025
## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm
1.Take the cost matrix that shows the cost between every pair of cities.

2.Generate all possible orders (permutations) in which the cities can be visited.

3.For each order, calculate the total travel cost, including returning to the starting city.

4.Keep track of the minimum total cost found so far.

5.After checking all possible orders, return the minimum cost as the final answer.  

## Program:

### To implement the program for TSP.
### Developed by: GOKULA PRIYA P  
### Register Number: 212222040044
```
from sys import maxsize
from itertools import permutations
V = 4
def travellingSalesmanProblem(graph, s):
    ##Write your code
    vertex = [] 
    for i in range(V): 
        if i != s: 
            vertex.append(i) 
    min_path = maxsize 
    next_permutation=permutations(vertex)
    for i in next_permutation:

        current_pathweight = 0
        k = s 
        for j in i: 
            current_pathweight += graph[k][j] 
            k = j 
        current_pathweight += graph[k][s] 
        min_path = min(min_path, current_pathweight) 
         
    return min_path
if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```
## Output:
![Screenshot 2025-05-24 203418](https://github.com/user-attachments/assets/35788818-6ca7-4ed5-8f03-6e41545c0baf)

## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
