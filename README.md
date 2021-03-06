# CISC372-Project

In this project, we attemtped to optimize the 2D Heat - Stencil Computation Problem.

Our serial code can be found at 
https://cdn-uploads.piazza.com/paste/is6hj59dz8a6n/ed26f861a603adef9153c15f0fbbd50448c89676d5bc63605a62b2d071cf5051/openacc-bookchapter-robfarber.pdf

We parallelized the serial code in the study above with OpenMP. 
We then compiled the code using NVHPC and GNU GCC with no optimization flags, -O1, -O2, and -O3.

**GNU GCC:**

    To compile the code using GNU GCC, first install the GCC Module on Bridges2 using the command: 

      module load gcc/10.2.0

    Then enter following command:

      gcc <optimization flag> -fopenmp <heat_Para.c or heat_serial.c> -o <serial, twothread, fourthread, or eightthread> 

**NVHPC:**

    To compile the code using NVHPC, first install the NVHPC Module on Bridges2 using the command:
  
      module load nvhpc/21.7
  
    Then enter following command:
  
      nvc <optimization flag> <-mp=multicore> <heat_Para.c or heat_serial.c> -o <serial, twothread, fourthread, or eightthread> 

**BATCH SCRIPT**

     To submit a job, in the <COMMAND HERE> space at the end of que.bat, enter the command:
     
       ./<serial, twothread, fourthread, or eightthread> <nj(ex. 2048)> <ni(ex. 2048)> <nsteps(ex. 10000)> <outputfile.out>  
    
**ENVIRONMENT SETUP**    
    
    To run the code using the batch script provided, change the email address on line 5 and run the following commands:

     RUN THIS COMMAND FIRST:
  
      export OMP_NUM_THREADS=<1,2,4, or 8>

    THEN:
  
      sbatch que.bat
