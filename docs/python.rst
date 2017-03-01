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
   Administrators group. See :doc:`permissions` for more information.

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
   * EPEL package - 5.0 / 2.7.10

* Jython

   * SCL Jython 2.7

You can use :doc:`deskctl` to install the various options, or read below for
the ``yum`` commands to use instead.

What implementation should I use?
---------------------------------

* If you want to use Python 2, and you don't need ``conda`` packages, then use
the RHEL system Python, and use ``pip`` to install packages.
* If you want to use Python 3, and you don't need ``conda`` pacakges, then use
the IUS Python 3.6 package and use ``pip3.6m`` to install pacakges
* If you need ``conda`` packages (Anaconda Python packages) then use miniconda

Recommended implementations
---------------------------

RHEL system Python
^^^^^^^^^^^^^^^^^^

Unless you need Python 3 or ``conda`` packages then we recommend you use the
system python in ``/usr/bin/python``. This is supported by Red Hat and kept
up to date with security and bug fixes. 

You can install packages by running ``sudo pip`` eg::

   sudo pip install numpy

IUS Python
^^^^^^^^^^

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
^^^^

Miniconda (Anaconda) 
^^^^^^^^^^^^^^^^^^^^

Other implementations 
------------------------

SCL Python
^^^^^^^^^^

EPEL Python
^^^^^^^^^^^
/
Jython
^^^^^^

