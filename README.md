# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input matrix dimensions and initialize augmented matrix and solution vector.

2.Populate the augmented matrix with user inputs.

3.Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.

4.Back substitute to compute solution values for the variables.

5.Print the solution vector formatted to two decimal places.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: S.PAVAN
RegisterNumber: 212225040296
'''

n = int(input())

a = []
for i in range(n):
    row = []
    for j in range(n+1):
        row.append(float(input()))
    a.append(row)
    
for i in range(n):
    for j in range(i+1,n):
        ratio = a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
x = [0] * n

for i in range(n-1,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]
    
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end = " ")
```

## Output:
<img width="1368" height="920" alt="image" src="https://github.com/user-attachments/assets/26378baf-773c-4624-99ea-27f19e6aa91d" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

