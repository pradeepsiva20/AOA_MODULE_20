# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start with the given set of numbers and the target sum.
2. Use a recursive function to try all combinations of elements (either include or exclude the current element).
3. At each recursive call, maintain a running sum of selected elements. If the sum exceeds the target, stop exploring that path.
4. If the running sum equals the target sum, return True indicating a subset has been found. 
5. If all elements are processed and no valid subset is found, return False.  

## Program:
```python
/*
Program to implement Subset sum problem.
Developed by: PRADEEP S 
Register Number: 212222100034
*/

def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a,i+1,sum,target,n)or SubsetSum(a,i+1,sum+a[i],target,n)  
    
    
    
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")


```

## Output:

![image](https://github.com/user-attachments/assets/a556d0f3-04f9-4b4a-96bb-fe59409e218c)



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
