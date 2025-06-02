# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start with an empty N×N chessboard. Initialize the board with all zeroes.
2. Place a queen in the leftmost column of the first row, then recursively attempt to place queens in the next columns.
3. Before placing a queen in a cell, check if it's safe by ensuring there are no other queens in the same row, upper-left diagonal, or lower-left diagonal. 
4. If placing a queen leads to a valid solution, move to the next column. If it leads to a dead-end, backtrack by removing the queen and trying the next row in the 
   current column.
5. Continue this process until all queens are placed or all possibilities are exhausted. If all queens are placed, print the board. 
   

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: PRADEEP S
Register Number: 212222100034
*/

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col >= N:
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col] = 1
            if solveNQUtil(board, col+1) == True:
                return True
            board[i][col] = 0
    return False        
        
      
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:
![image](https://github.com/user-attachments/assets/2a113d82-4867-4cf6-a084-a23565b67f22)



## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
