# Algorithm for QR Decomposition
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
4.	Construct the upper triangular matrix
	
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: DIVYA.A
RegisterNumber: 212222230034
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    Q = np.empty((n,n))
    u = np.empty((n,n))
    
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0] / np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        
        u[:,i] = A[:,i]
        for j in range(i):
            u[:,i]-= (A[:,i] @ Q[:,j]*Q[:,j])
            
        Q[:,i] = u[:,i] / np.linalg.norm(u[:,i])
            
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:,j] @ Q[:,i]
    print(Q)
    print(R)
  
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![math exp 08(1)](https://github.com/Divya110205/QRdecomposition/assets/119404855/6884609c-f629-4a1a-91ac-4d2275c30cad)
![math exp 08(2)](https://github.com/Divya110205/QRdecomposition/assets/119404855/cc52464e-c234-4895-bfc9-f0020bfdfc9c)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
