# HOW TO USE THE CODE
from your terminale, inside the directory of the files, tiping "make" will trigger the makefile generating in cascades two HDF5 file containing the x and y vector and printing on the terminal the output. These informaions
are also passed to the second script "Calculations.c" which takes a configFile which contains the constants a, N and the directories of HDF5 files. Calculation.c script will create the final file containing the vector
d obtianed from d = ax + y (in the code is gsl_vector_axpby(a, x, 1.0, y)). This result is also printed on the terminal.
