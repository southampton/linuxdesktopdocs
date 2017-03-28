OpenMPI
=======

OpenMPI is the defacto standard implementation of the Message Passing Interface
system. OpenMPI allows developers to create programs that scale across multiple 
machines.

Available versions
------------------

Several versions of OpenMPI are available for use:

* Compiled by gcc 4.8

   * 1.10.3 (Red Hat package)
   * 1.10.6
   * 2.0.2

* Compiled by gcc 6.2

   * 1.10.6
   * 2.0.2
   * 2.1.0

* Compiled by icc (Intel)

   * 1.10.6
   * 2.0.2

* Compiled by PGI

   * 1.10.6
   * 2.0.2

The implementations are either compiled with the GNU Compiler Collection (GCC),
the Intel C/C++ compiler (icc) or the PGI C/C++ compiler. You can use the 
implementation and version based on the C/C++ compiler you've chosen to use. All
of the GCC versions have been compiled with the RHEL7 default GCC (GCC 4.8). On 
request we will compile additional versions with newer versions of GCC.

Installing OpenMPI
------------------

Select a version and then run the command for that version listed below. You
can install all of the different versions at the same time:

* 1.10.3 (gcc 4.8): ``sudo yum install openmpi``
* 1.10.6 (gcc 4.8): ``sudo yum install openmpi1106``
* 1.10.6 (gcc 6.2): ``sudo yum install openmpi1106-gcc62``
* 1.10.6 (icc): ``sudo yum install openmpi1106-intel``
* 1.10.6 (pgi): ``sudo yum install openmpi1106-pgi``
* 2.0.2 (gcc 4.8): ``sudo yum install openmpi202``
* 2.0.2 (gcc 6.2): ``sudo yum install openmpi202-gcc62``
* 2.0.2 (icc): ``sudo yum install openmpi202-intel``
* 2.0.2 (pgi): ``sudo yum install openmpi202-pgi``
* 2.1.0 (gcc 6.2): ``sudo yum install openmpi210-gcc62``

Using OpenMPI
-------------

All of the OpenMPI implementations use the :doc:`envmodules`. Thus to use
an implementation simply ``module load`` the version you prefer:

* 1.10.3 (gcc 4.8): ``module load mpi/openmpi-x86_64``
* 1.10.6 (gcc 4.8): ``module load openmpi/1.10.6``
* 1.10.6 (gcc 6.2): ``module load openmpi/1.10.6-gcc62``
* 1.10.6 (icc): ``module load openmpi/1.10.6-intel``
* 1.10.6 (pgi): ``module load openmpi/1.10.6-pgi``
* 2.0.2 (gcc 4.8): ``module load openmpi/2.0.2``
* 2.0.2 (gcc 6.2): ``module load openmpi/2.0.2-gcc62``
* 2.0.2 (icc): ``module load openmpi/2.0.2-intel``
* 2.0.2 (pgi): ``module load openmpi/2.0.2-pgi``
* 2.1.0 (gcc 6.2): ``module load openmpi/2.1.0-gcc62``
