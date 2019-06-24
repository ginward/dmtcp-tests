# dmtcp-tests

A simple example that demonstrates how to use DMTCP to checkpoint serial jobs. 

Compile example.cpp using the following
    
    mkdir build
    cd build
    cmake -DCMAKE_C_COMPILER=/usr/local/software/spack/current/opt/spack/linux-rhel7-x86_64/gcc-7.2.0/openmpi-4.0.1-myumauelaffayqdjhfbuzh6w6n7tx3dz/bin/mpicc -DCMAKE_CXX_COMPILER=/usr/local/software/spack/current/opt/spack/linux-rhel7-x86_64/gcc-7.2.0/openmpi-4.0.1-myumauelaffayqdjhfbuzh6w6n7tx3dz/bin/mpic++ ..

There are two example submission slurm scripts. One uses a job array to submit multiple serial jobs and the another uses the srun command. Both scripts run the call_dmtcp script which takes two arguments. The first is the executable with its arguments and the second is the number of seconds after the start of the executable the dmtcp with generate a checkpoint. After the generation of the checkpoint the executable will exit.

To restart the jobs just resubmit the slurm script.