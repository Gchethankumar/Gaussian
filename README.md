# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. At first, we have imported the necessary libraries we will use in our program.
2. Read Number of Unknowns: n
3. Read Augmented Matrix (A) of n by n+
4. Transform Augmented Matrix (A) to Upper Trainagular Matrix by Row Operations.
5. After that, we applied the Gaussian elimination method.
6. After that, we apply the back substitution method to obtain the desired output.
7. Display Result.

## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: G.Chethan Kumar
RegisterNumber: 212222240022

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exist('Divide by Zero found')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
X[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i]=a[i][n]
    for j in range(i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
    X[i]=X[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,X[i]),end=' ')
```

## Output:

![Screenshot 2023-04-29 204949](https://user-images.githubusercontent.com/118348224/235310394-8e34fea1-e0e0-463f-b0d4-d71445d69cdf.png)

## Result:

Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

