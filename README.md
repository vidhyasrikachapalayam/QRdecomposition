# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

  ![ex4](https://user-images.githubusercontent.com/119477817/215305428-890545cd-b8b4-40bc-bfc4-f67263b4cc19.jpg)


   ![ex6](https://user-images.githubusercontent.com/119477817/215305444-6bda2714-fade-449a-a9f9-bd1b26754d60.jpg)


   ![ex3](https://user-images.githubusercontent.com/119477817/215305457-d5c222cb-0c86-44ab-9f27-992940037f03.jpg)


3.	Obtain the Q matrix   
    ![ex1](https://user-images.githubusercontent.com/119477817/215305470-a1d40e78-1326-4d89-a2a8-5b45626df327.jpg)

4.	Construct the upper triangular matrix R
    ![ex2](https://user-images.githubusercontent.com/119477817/215305481-d60a2b93-f3de-4f6b-9cd8-45c4a22bdc05.jpg)




## Program:
### Gram-Schmidt Method



Program to QR decomposition using the Gram-Schmidt method

Developed by: your name:vidhyasri.k


RegisterNumber: 22008468

import numpy as np

def QR_decomposition(A):

    n, m=A.shape
    Q = np.empty((n, n)
    u = np.empty((n, n))
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    for i in range(1,n):
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j] * Q[:, j])
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
    R = np.zeros((n,m))
    for i in range(n):
       for j in range(i, m):
           R[i ,j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))

QR_decomposition(a)







## Output

![QR](https://user-images.githubusercontent.com/119477817/215305487-0270b923-a67f-4726-9c40-a576c599ec42.png)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
