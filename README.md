# Multilevel-Ensemble-Kalman-Bucy-Filter

This repository contains an implementation of the Multilevel Ensemble Kalman Bucy Filter. Code for HPC implementation with MPI cores, designed to run on Supercomputer Shaheen is also included. The algorithm deals with linear Gaussian filtering problems in continuous time and has appealing performance in high dimensions. A Deterministic Multilevel Ensemble Kalman Bucy Filter is also constructed in the Jupyterbook. 

Many thanks to my collaborators: Prof.Ajay Jasra and Dr.Neil Chada

If you are interested in using this code, please cite our paper which describes this methodology:
Multilevel Kalman Bucy Filter https://arxiv.org/abs/2011.04342

Description:

1. The main folder contains the main function, including the (deterministic) ensemble Kalman-Bucy filter (EnKBF), (deterministic) coupled ensemble Kalman-Bucy filter (CEnKBF), as well as the (deterministic) multilevel Ensemble Kalman-Bucy filter. A model-generation function is also included for 10 dimensional implemtations. Details for parameter tuning are also provided there.
2. The HPC (High Performance Computation) simulation folder includes codes for parameter tuning and (D-)MLEnKBF simulations which can be done on Supercomputing platform. MPI4py packages are used here and we perform the simulation on KAUST supercomputer Shaheen on 1024 MPI cores. To implement (D)MLEnKBF successfully, parameter tuning is required on (D)EnKBF and (D)CEnKBF to choose the optimal number of ensemble sizes at each level for (D)MLEnKBF. For High dimesional Implementation, we assume all the matrices in our model are of block diagonal structure, with each block of shape 10*10. Then the high dimensional implementaion of EnKBF/MLEnKBF can be seperated into block-wise implementation. And the high dimensional result can be obtained by compiling results at low dimension. The scaling power of supercomputer allow us to perform simulation in parallel and thus accelerate the computation.
3. Test folder includes some test on the main functions.  

Packages used:

Numpy, Scipy, Matplotlib, MPI4py, ipyparallel, progressbar, re, json, ast, warnings, time, datetime

Platform:  

Shaheen cluster with 32 nodes, 1024 cores. KAUST supercomputer.


@Fangyuan_ksgk
