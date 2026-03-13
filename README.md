# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read n, matrix A, and vector B; initialize solution vector X.
2. Convert A to upper triangular form using forward elimination.
3. Compute unknowns using back substitution.
4. Print the solution vector X

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Deepadharshini T
RegisterNumber: 212224230052
*/
```
```
import numpy as np
n=int(input())
a,b=[],[]
for i in range(n):
    t=[]
    for j in range(n):
        t.append(int(input()))
    a.append(t)
    b.append(int(input()))
n=len(b)
x=[0]*n 
for k in range(n):
    for i in range(k+1,n):
        factor = a[i][k]/a[k][k]
        for j in range(k,n):
            a[i][j]=a[i][j]-factor*a[k][j]
        b[i]=b[i]-factor*b[k]
    for i in range(n-1,-1,-1):
        sum_ax=0
        for j in range(i+1,n):
            sum_ax+=a[i][j]*x[j]
        x[i]=(b[i]-sum_ax)/a[i][i]
for i in range(len(x)):
    print(f"X{i} = {x[i]:.2f}",end=" ")
```

## Output:
<img width="1032" height="433" alt="image" src="https://github.com/user-attachments/assets/5a3ff57d-de20-450f-9d9a-1ca70f2801c5" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
