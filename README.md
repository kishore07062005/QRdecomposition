# EX-8:QR Decomposition
### DATE:
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
#Developed by: Rahul M R
#Register number: 2305003005

import numpy as np
def QR_decomposition(A):
    n,m=A.shape
    Q = np.empty((n,n))
    u= np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j]*Q[:,j])
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_decomposition(a)
```

## Output
![8](https://github.com/kishore07062005/QRdecomposition/assets/156066116/272c881e-9a62-4003-8102-321fbe7fbd4b)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
