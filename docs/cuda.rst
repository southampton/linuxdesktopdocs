CUDA
====

CUDA is a mechanism for allowing general purpose computing on graphics cards
rather than the normal CPU. It is thus optimised for parallel computing and 
high memory throughput. CUDA requires a CUDA-enabled graphics processing unit
(GPU) which means a NVIDIA graphics card is required.

Installing CUDA
---------------

The NVIDIA CUDA software repository is available on the Linux desktop platform
so you can install the various versions like this:

* 8.0: ``sudo yum install cuda-8-0``
* 7.5: ``sudo yum install cuda-7.5``
* 7.0: ``sudo yum install cuda-7-0``

This installs the official NVIDIA CUDA packages. CUDA is installed into::

   /usr/local/cuda-N.N/

Where N.N is the version, e.g. ``/usr/local/cuda-8.0``. To add CUDA to your path
add this to your ``.bashrc``::

   export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}

Using CUDA Samples
------------------

Once installed you can deploy and build the CUDA samples like this::

   mkdir ~/cuda
   /usr/local/cuda-8.0/bin/cuda-install-samples-8.0.sh ~/cuda
   cd ~/cuda/NVIDIA_CUDA*
   make

That will build *all* the samples, which you probably don't want. Instead 
change into a sample sub directory and build just one at at time, like so::

   cd ~/cuda/NVIDIA_CUDA*/0_Simple/clock/
   make

You can then run the compiled ``clock`` like so::

   [db2z07@uos-212247 clock]$ ./clock
   CUDA Clock sample
   GPU Device 0: "GeForce GTX 750 Ti" with compute capability 5.0
   
   Average clocks/block = 4042.890625

