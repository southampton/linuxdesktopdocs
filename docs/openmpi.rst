OpenMPI
=======

OpenMPI is the defacto standard implementation of the Message Passing Interface
standard. OpenMPI allows programmers to create programs that scale across 
multiple machines.

Available versions
------------------

At the time of writing five versions of OpenMPI are avaialble for use:

* Red Hat OpenMPI 1.10.3 (gcc)
* UoS OpenMPI 1.10.6 (gcc)
* UoS OpenMPI 1.10.6 (icc)
* UoS OpenMPI 2.0.2 (gcc)
* UoS OpenMPI 2.0.2 (icc)

The implementations are either compiled with the GNU Compiler Collection (GCC)
or with the Intel C/C++ compiler (icc) - this way you can use an implementation
based on the C/C++ compiler you've chosen to use. All of the GCC versions have
been compiled with the RHEL7 default GCC (GCC 4.8). On request we will compile
additional versions with newer versions of GCC.

Installing OpenMPI
------------------

Select a version and then run the command for that version listed below. You
can install all of the different versions at the same time:

* 1.10.3 (gcc): ``sudo yum install openmpi``
* 1.10.6 (gcc): ``sudo yum install openmpi1106``
* 1.10.6 (icc): ``sudo yum install openmpi1106-intel``
* 2.0.2 (gcc): ``sudo yum install openmpi202``
* 2.0.2 (icc): ``sudo yum install openmpi202-intel``

Using OpenMPI
-------------

All of the OpenMPI implementations use the :doc:`envmodules`. Thus to use
an implementation simply ``module load`` the version you prefer:

* 1.10.3 (gcc): ``module load mpi/openmpi``
* 1.10.6 (gcc): ``sudo yum install openmpi1106``
* 1.10.6 (icc): ``sudo yum install openmpi1106-intel``
* 2.0.2 (gcc): ``sudo yum install openmpi202``
* 2.0.2 (icc): ``sudo yum install openmpi202-intel``

