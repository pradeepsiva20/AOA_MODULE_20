# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start with a maze represented as a 2D list, where 1 indicates a valid cell and 0 indicates a blocked cell.
2. Create a solution matrix initialized with zeros to keep track of the path.
3. Define a recursive function solveMazeUtil(x, y, sol) that tries to move the rat from the current cell (x, y) to the destination. 
4. Check if the current cell is safe to move using isSafe(). If so, mark it as part of the solution path. Then recursively try to move either down (x+1, y) or 
   right (x, y+1). 
5. If moving in either direction does not give a solution, backtrack by unmarking the current cell and return false. If the destination is reached, return true. 

## Program:
```python
/*
Program to implement Rat in a Maze.
Developed by: PRADEEP S
Register Number: 212222100034
*/

N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    
    if x == N-1 and y==N-1:
        sol[x][y]=1
        return True
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze, x+1,y,sol)==True:
            return True
        if solveMazeUtil(maze, x,y+1,sol)==True:
            return True
        sol[x][y]=0
        return False
        

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)

```

## Output:

![image](https://github.com/user-attachments/assets/eee0bd54-95da-4a4f-89d9-c1487085dbe1)



## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
