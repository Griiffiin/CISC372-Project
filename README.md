# CISC372-Project

In this project, we attemtped to optimize the 2D Heat - Stencil Computation Problem.

Our serial code can be found at 
https://cdn-uploads.piazza.com/paste/is6hj59dz8a6n/ed26f861a603adef9153c15f0fbbd50448c89676d5bc63605a62b2d071cf5051/openacc-bookchapter-robfarber.pdf

We parallelized the serial code in the study above with OpenMP. 
We then compiled the code using NVHPC and GNU GCC with no optimization flags, -O1, -O2, and -O3.

GNU GCC:

To compile the code using GNU GCC, run the following command:
gcc <optimization flag> -fopenmp <heat_Para.c or heat_serial.c> -o <serial, twothread, fourthread, or eightthread> 
  
To run the code using the batch scripts provided change the email address on line 5 and run the following commands:
export OMP_NUM_THREADS=<1,2,4, or 8>
sbatch <serial, twothread, fourthread, or eightthread>.sh
