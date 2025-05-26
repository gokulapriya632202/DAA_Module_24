# EX 6D BRUTE FORCE ALGORITHM
## DATE: 10/04/2025
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.

## Algorithm
1. Take two inputs: the main string and the substring to search for.
2. Create a regex pattern using the substring.
3. Search for the first match of the pattern in the main string.
4. If a match is found.Print the starting index of the match.
5. Continue searching for the next match, starting just after the current match.
6. Repeat step 4 until no more matches are found.

## Program:

### To implement the program using brute force method of searching for the given substring in the main string.
### Developed by: GOKULA PRIYA P  
### Register Number: 212222040044
```
def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]
    for i in range(l-ls+1):
        if string[i:i+ls]==sub:
            print(f"Found at index {i}")

    ########### Add your code here #######

str1=input()
str2=input()
```
## Output:
![Screenshot 2025-05-24 203646](https://github.com/user-attachments/assets/b0ed0843-5764-4a0b-af23-49498c513d66)

## Result:
Thus the above program was executed successfully for searching the substring at respective index.
