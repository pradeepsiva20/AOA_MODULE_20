## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Start by creating an adjacency matrix representation of the graph and initialize a color array for vertices.
2. Define a utility function that tries to assign colors to each vertex recursively, starting from vertex 0.
3. Before assigning a color, check whether it's safe by verifying that no adjacent vertex has the same color.
4. If it’s safe, assign the color and recursively call the function for the next vertex. If assigning the color leads to no solution, backtrack and try another 
   color. 
5. If all vertices are successfully colored, print the color assignment; otherwise, indicate that no solution exists.
  

## Program:
```python
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: PRADEEP S
Register Number: 212222100034
*/

class Graph():
    def __init__(self,vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i]==c:
                return False
        return True
    def graphColourUtil(self,m,colour,v):
        if v == self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c)==True:
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1) == True:
                    return True
                colour[v] = 0
    def graphColouring(self,m):
        colour = [0]*self.V
        if self.graphColourUtil(m,colour,0) == None:
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end=' ')
        return True    
```

## Output:

![image](https://github.com/user-attachments/assets/a2119942-d5e2-47a0-be60-9ed7aa328118)



## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
