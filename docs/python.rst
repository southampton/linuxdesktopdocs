Python
======

Python is a popular and versatile programming language used in many scientific
disiplines across the university. It is by far the most popular language in use
by staff at Southampton and is the most used tool on Windows desktops too!

The university Linux desktop platform has a large number of Python 
implementations for you to choose from. We've worked hard to try to provide 
the options you might need and granted you the privileges needed to install 
packages as required.

.. note::

   To install python modules via ``sudo pip`` you need to be in the 
   Administrators group. See :doc:`permissions` for more information. You don't
   need to be in this group to use the ``conda`` command. You can also use 
   ``pip`` directly, without ``sudo``, and install packages in your home 
   directory.

List of available implementations
---------------------------------

* CPython

   * RHEL system python - 2.7.5
   * Miniconda (Anaconda) - 2.7, 3.6
   * IUS packages - 3.4.6, 3.5.3, 3.6.0
   * SCL packages - 2.7.8, 3.3.2, 3.4.2, 3.5.1
   * EPEL package - 3.4.5

* PyPy

   * PyPy 5.6 - 2.7.12
   * PyPy3 5.5-alpha - 3.3

* Jython

   * SCL Jython 2.7

You can use :doc:`deskctl` to install the various options, or read below for
the ``yum`` commands to use instead.

Which implementation should I use?
---------------------------------

* If you want to use Python 2, and you don't need ``conda`` packages, then use the RHEL system Python, and use ``pip`` to install packages.
* If you want to use Python 3, and you don't need ``conda`` pacakges, then use the IUS Python 3.6 package and use ``pip3.6m`` to install pacakges
* If you need ``conda`` packages (Anaconda Python packages) then use miniconda

RHEL system Python
------------------

Unless you need Python 3 or ``conda`` packages then we recommend you use the
system python in ``/usr/bin/python``. This is supported by Red Hat and kept
up to date with security and bug fixes. 

You can install packages by running ``sudo pip`` eg::

   sudo pip install numpy

IUS Python
----------

The IUS repository provides Python 3 packages for Red Hat Enterprise Linux. If
you need to use Python 3 then we recommend you use the IUS Python packages. 
Several versions are available for install:

* Python 3.4 - ``sudo yum install python34u python34u-pip``
* Python 3.5 - ``sudo yum install python35u python35u-pip``
* Python 3.6 - ``sudo yum install python36u python36u-pip``

You can then use Python via the following paths to the binary:

* Python 3.4 - ``/usr/bin/python3.4``
* Python 3.5 - ``/usr/bin/python3.5``
* Python 3.6 - ``/usr/bin/python3.6``

The version of Python in ``/usr/bin/python3`` depends on the order the IUS
packages are installed, so we don't recommend you use that path. 

You can install packages via ``sudo pip``:

* Python 3.4 - ``sudo pip3.4``
* Python 3.5 - ``sudo pip3.5``
* Python 3.6 - ``sudo pip3.6``

For example, to install ``numpy`` on IUS Python 3.6::

  sudo pip3.6 install numpy

PyPy
----

PyPy is a just-in-time (JIT) compiler for Python which aims to be compatible
with the standard CPython implementation. Using PyPy often yields significant
performance benefits.

To install PyPy run the following command::

   sudo yum install pypy256

This installs PyPy 5.6 which is compatible with CPython 2.7.12.

To install PyPy3 run the following command::

   sudo yum install pypy3355

This installs PyPy3 5.5-alpha which is compatible with CPython 3.3.5.

To run PyPy you can either use the following paths:

* ``/usr/bin/pypy56`` - PyPy 5.6 (Python 2.7.12)
* ``/usr/bin/pypy3355`` - PyPy 5.5-alpha (Python 3.3.5)

Or you can use the ``module`` system:

* ``module load pypy/5.6`` - PyPy 5.6 (Python 2.7.12)
* ``module load pypy/3.3-5.5`` - PyPy 5.5-alpha (Python 3.3.5)

Once you've loaded the module you can use the ``pypy`` command directly and
it will correspond to the version of pypy you chose to load.

You can install packages with ``pip``:

* ``sudo /local/software/pypy/5.6/bin/pip`` - PyPy 5.6 (Python 2.7.12)
* ``sudo /local/software/pypy/3.3-5.5/bin/pip3`` - PyPy 5.5-alpha (Python 3.3.5)

For example, to install ``numpy`` on PyPy 5.6::

   sudo /local/software/pypy/5.6/bin/pip install numpy

Miniconda (Anaconda)
--------------------

Anaconda, and its ``conda`` package manager, is an alternative to the ``pip``
package manager (although the developers insist it complements pip and solves
different problems). 

Anaconda, conda and miniconda are not designed for "system-wide" use, they are 
intended for individual users to download and install for just that one user. 
Better multi-user support is planned, but as of March 2017, is not yet 
available. 

To use ``conda`` you don't need to download and install Anaconda or miniconda
yourself, instead you can get started by installing ``miniconda`` which just
contains ``conda`` and ``python``::

   sudo yum install miniconda

Once installed you can use ``conda`` to create a new environment within your
home directory with whatever version of Python and whichever Python packages
you need.

You should start by creating an environment, e.g::

   conda create -n yourenvname python=x.x

You specify the version of python you want with the ``python=x.x`` flag, but 
this is optional and if omitted conda will use the version of Python shipped 
with ``miniconda`` which at the time of writing is Python 3.6.0.

You can specify at creation time the packages you want installed. For example,
to install the entire anaconda set of packages you can do the following::

   conda create -n yourenvname python=3.6 anaconda

You can then use your new environment like so::

   source activate yourenvname

And you can then stop using it like so::

   source deactivate

You can install additional packages with ``conda``::

   conda install -n yourenvname [package]

And if you want to delete an environment do the following::

   conda remove -n yourenvname -all

SCL Python
----------

.. note::

   The SCL python33 package conflicts with the IUS Python packages. You
   cannot have both versions installed at the same time. To install the SCL
   python33 package you must first remove the IUS Python packages. In any case
   we strongly recommend you use the IUS packages rather than SCL.

Red Hat provides several CPython packages as part of its "Software Collections"
system. These packages are generally older than the IUS packages and are more
difficult to use - they require the use of the ``scl`` command. At the time
of writing the following versions are available:

* Python 2.7.8 - ``sudo yum install python27 python27-python-pip`` 
* Python 3.3.2 - ``sudo yum install python33``
* Python 3.4.2 - ``sudo yum install rh-python34 rh-python34-python-pip``
* Python 3.5.1 - ``sudo yum install rh-python35 rh-python35-python-pip``

Once installed you can't use python until you use the ``scl`` command
which is somewhat like the environment module system:

* Python 2.7.8 - ``scl enable python27 bash``
* Python 3.3.2 - ``scl enable python33 bash``
* Python 3.4.2 - ``scl enable rh-python34 bash``
* Python 3.5.1 - ``scl enable rh-python34 bash``

Once you've run the ``scl`` command then the ``python`` command will now be the
version of Python you requested. The ``pip`` command will also be updated
for the SCL python, but it won't work unless you use a special ``sclsudo`` 
command we've created. So to install packages you should run::

   sclsudo pip install numpy

EPEL Python
-----------

.. note::

   The EPEL python 3.4 package conflicts with the IUS Python 3.4 package. You
   cannot have both versions installed at the same time. To install the EPEL
   python you must first remove the IUS Python 3.4 packages. In any case
   we strongly recommend you use the IUS packages rather than EPEL.

Another alternative Python 3 package is provided by EPEL. We recommend that
you use the IUS packages instead since the EPEL Python package is now quite
out of date. If you do want to use it, install it like so::

   sudo yum install python34 python34-pip

You can then use the package with the binary path::

   /usr/bin/python3.4

and you can install packages with ``pip``::

   sudo /usr/bin/pip3.4 install numpy

Jython
------

Jython is an implementation of Python running on the Java virtual machine (JVM).
Red Hat have provided a packaged version of Jython as part of their Developer
Toolset 4 product. To install it run this command::

   sudo yum install devtoolset-4 devtoolset-4-jython

Then run the ``scl`` command to enable it::

   scl enable devtoolset-4 bash

You can then run jython directly::

   jython
