## python source  code

```python
import numpy as np;     #for arrays
import time;            #for  timer

#............variable declaration...........#
a = 3;
arrayDim = 10;          #change for the array dimension (10, 10^6, 10^8)
matDim = 10;            #matrix dimension: 10, 100, 10000
xv = 0.1;
yv = 7.1;
check = 0;
check2 = 0;

#arrays
x = np.empty(arrayDim);
y = np.empty(arrayDim);
d = np.empty(arrayDim);

#matrices
A = np.empty((matDim, matDim));
B = np.empty((matDim, matDim));
C = np.empty((matDim, matDim));
D = np.empty((matDim, matDim));

start = time.time();      #take the time

# ====================================================================================================== #
#...............filling the arrays............#
for i in range(arrayDim) :
    x[i] = xv;
    y[i] = yv;
    #d[i] = x[i] * a + y[i];
    #x = np.append(x, xv);
    #y = np.append(y, yv);


#...............calculations...................#
d = x*a + y;

#...............check..........................#
for i in range(len(d)): 
    check += d[i];
if round(check) == ((a*xv + yv)*arrayDim): print("the array is correct")
else : print("you suck at coding");

middle = time.time();     #take the time againg

#print the time
print(f"first time: {middle - start}");


# ========================================================================================== #
#filling matrices
for i in range(matDim):
    for j in range(matDim):
        A[i][j] = a;
        B[i][j] = yv;

#...............calculations...................#
#matrix product
C = np.dot(A, B);
#element by element product
D = A * B;

#...............check..........................#
for i in range(matDim): 
    for j in range(matDim):
        check2 += D[i][j];
if round(check2) == round((a * yv * pow(matDim, 2))) : print("the array is correct")
else : print("you suck at coding");


end = time.time();
print(f"end time: {end - start}");
```

# C source code

```C
#include <stdio.h> 
#include <math.h>

int main() {
	
	//variable  declaration
	int a = 3;
	double xv = 0.1;
	double yv = 7.1;
	int dimArray = 10;                   //array dimension: 10, 10^6, 10^8
	int dimMat = 100;                      //matrix dimension: 10, 100, 10000
		
	double check = 0.0;
	double check2 = 0.0;
	
	double x[dimArray];
	double y[dimArray];
	double d[dimArray];
	
	double A[dimMat][dimMat];
	double B[dimMat][dimMat];
	double C[dimMat][dimMat];
	double D[dimMat][dimMat];


	//filling arrays
	for (int i = 0; i < dimArray; i++) {
		x[i] = xv;
		y[i] = yv;
		d[i] = a * x[i] + y[i];
		//printf("%f, ", d[i]);
	}

	//check 
	for (int i = 0; i < dimArray; i++) {
		check += d[i];
	}
	if (round(check) == round((a * x[0] + y[0]) * dimArray)) printf("good job");
	else printf("you suck at coding");
	

	//filling the matrices
	for (int i = 0; i < dimMat; i++) {
		for (int j = 0; j < dimMat; j++) {
			A[i][j] = a;
			B[i][j] = yv;
			//element by element product
			D[i][j] = A[i][j] * B[i][j];
			//printf("%f, ", D[i][j]);
		}
	}
	//matrix product
	for (int i = 0; i < dimMat; i++) {
		for (int j = 0; j < dimMat; j++){
			for (int k = 0; k < dimMat; k++){
				C[i][j] += A[i][k] * B[k][j];
			}
		}
	}
	
	//print the matrix C
	//for (int i = 0; i < dimMat; i++) {
	//	for (int j = 0; j < dimMat; j++) {
	//		printf("%f, ", C[i][j]);
	//	}
	//}

	//check 2
	for (int i = 0; i < dimMat; i++) {
		for (int j = 0; j < dimMat; j++) {
			check2 += D[i][j];
		}
	}
	if (round(check2) == round(A[0][0] * B[0][0] * pow(dimMat, 2))) printf("good job");
	else printf("you suck at coding");
}
```

## Question: did you find any problems in running the codes for some N. If so, do you hane any idea why?
using python and N 10^8 was actually slow (roughly 35s). I think the reason is because it is an interpreted language, so it read line by line and it also don't use specified variable (but C does).

## Question: Were you able to test correctly the sum and product of points 1-3? If so, how? If not, what was the problem?
I actually did it. As you can see from my code, i simply used a for loop  to sum all the elements inside the array/matrix, then i just checked if that value is the same as the one i expect inside the array/matrix. 
The problem with this method is the floating numbers tends to be roughly what you expect (39.99999999999 instead of 40 for example) so confronting them gived a wrong result. The simple solution was to round the values.
Another solution i could try is to check if the two numbers are equals inside a certain value (in this case 0.001 would be enough).
Of course this method works because we used simple matrices with the same value for every position.
