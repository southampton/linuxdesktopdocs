Fortran
=======

Fortran is a general-purpose, imperative programming language that is especially 
suited to numeric computation and scientific computing. FORTRAN was developed
in the 1950s making it one of the oldest languages still in use. It is often
use for computational chemistry and fluid dynamics. 

List of compilers
-----------------

Several C and C++ compilers are available on the Linux desktop platform:

* gFortran (Part of the GNU compiler collection)

   * v4.8 - Red Hat's built in gFortran
   * v4.9 - part of :doc:`rhdt` 3
   * v5.3 - part of :doc:`rhdt` 4
   * v6.2 - part of :doc:`rhdt` 6

* PGI Fortran

   * N/A (not yet packaged, coming soon!)

GCC 
---

Several versions of gFortran are available. The standard version, tied to the 
system GCC version, is v4.8 You can install it like so::

   sudo yum install gcc-gfortran

Later versions are available as part of the :doc:`rhdt` bundles:

* v4.9: ``sudo yum install devtoolset-3-gcc-gfortran``
* v5.3: ``sudo yum install devtoolset-4-gcc-gfortran``
* v6.2: ``sudo yum install devtoolset-6-gcc-gfortran``

Once you have installed the packages you need to use :doc:`scl` to use the 
updated version of gfortran like so::

* v4.9: ``scl enable devtoolset-3 bash``
* v5.3: ``scl enable devtoolset-4 bash``
* v6.2: ``scl enable devtoolset-6 bash``

Once those commands are run then running 'gfortran' will run the version you 
requested.

See the :doc:`softwarecollections` document for more information on using :doc:`scl`.

PGI Fortran
-----------

We have not yet packaged this, although it will be done soon!
