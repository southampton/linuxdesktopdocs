C and C++
=========

C is a general-purpose, low level, imperative computer programming language, 
supporting structured programming, lexical variable scope and recursion, while 
a static type system prevents many unintended operations. C++ is an extension 
of C within object-oriented features and a much larger standard library.

List of compilers
-----------------

Several C and C++ compilers are available on the Linux desktop platform:

* GCC (GNU compiler collection)

   * v4.8 - Red Hat's built in GCC
   * v4.9 - part of :doc:`rhdt` 3
   * v5.3 - part of :doc:`rhdt` 4
   * v6.2 - part of :doc:`rhdt` 6

* ICC (Intel compiler suite)

   * N/A (not yet packaged, coming soon!)

* Clang (LLVM C/C++ compiler)

   * v3.9.1
   * v3.4.2 from the :doc:`epel` project

GCC 
---

Several versions of GCC are available. The system gcc - the one used to build
Red Hat Enterprise Linux 7 - is version 4.8. You can install it like so::

   sudo yum install gcc gcc-c++

Later versions are available as part of the :doc:`rhdt` bundles:

* v4.9: ``sudo yum install devtoolset-3-gcc devtoolset-3-gcc-c++``
* v5.3: ``sudo yum install devtoolset-4-gcc devtoolset-4-gcc-c++``
* v6.2: ``sudo yum install devtoolset-6-gcc devtoolset-6-gcc-c++``

Once you have installed the packages you need to use :doc:`scl` to use the 
updated version of gcc like so::

* v4.9: ``scl enable devtoolset-3 bash``
* v5.3: ``scl enable devtoolset-4 bash``
* v6.2: ``scl enable devtoolset-6 bash``

Once those commands are run then running 'gcc' will run the version you 
requested.

See the :doc:`softwarecollections` document for more information on using :doc:`scl`.

ICC
---

We have not yet packaged the Intel Parallel Suite.

LLVM Clang
----------

Clang is the compiler from the LLVM project. To use it first install the latest
version at the time of writing::

   sudo yum install llvm391

The LLVM package includes:

* LLVM core libraries
* Clang
* compiler-rt
* LLDB (LLVM debugger)
* LLD (LLVM linker)

Once installed you should use the :doc:`envmodules` to use clang itself::

   module load llvm/3.9.1

See :doc:`envmodules` for more information on using the module system.
