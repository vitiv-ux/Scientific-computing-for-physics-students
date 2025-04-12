# INTRODUCTION
In this script a matrix A  is created. To achieve rank 2 this solution  is proposed: first 2 gaussian distributed vectors (dimention 1000) are created, then the external product of the two vectors is applied
resulting in the matrix A (1000x1000). A is then normalized so that the mean and the standar deviation are 1. The results are printed. I think the result is not perfect though and to see the difference a second matrix B (1000x1000) with mean and standard devation 1 is created. The two matrices are then plotted against a theoretical result to see the difference. FFT c2c and r2c are calculated using numpy with the following 
functions: np.fft.fft2 and np.fft.rfft2.  To obtain the A matrix from these  two the following functions are applied: np.fft.ifft2 and np.fft.irfft2. Lastly the errors  are calcolated. 

# ARE ERRORS REACHING MACHINE PRECISION?
In both the cases (c2c and r2c) the results printed from the script reach a value close to the machine precision 2.22E-16 exept for the mean relative error which is around E-13. This is probably due to the way errors are calculated. In fact np.mean and np.sqrt can cause loss in precision. Other loss of precision could be introduced by the FFT as it can introduce approximations. 

# C[0,0] AND R[0,0]
The result is 1000000 for both the matrices. This result is obtained by the definition of how the FFT is calculate as the [0,0] correspond to the product of the mean value of the matrix by its size (1x1000000) which is the frequency zero. 
