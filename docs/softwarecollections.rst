Software collections (SCL)
==========================

Sofware collections - or SCL - is a collection of 'add-on' software packages
created and maintained by Red Hat. They were created in order to deliver
more up to date versions of software to customers on Red Hat Enterprise Linux
which typically does not update software "mid-life" of a product. Via SCL Red 
Hat is able to provide more recent stable versions of software for customers
to use without affecting the stability and security of the base product.

Due to our education licence all SCL software is available to users of our
linux desktops. More information about all the available packages can be found
on the dedicated `software collections website <https://www.softwarecollections.org/en/scls/>`_.

How to install SCL packages
---------------------------

SCL packages are normal rpm software packages and thus can be installed via the
usual tools, see :doc:`software` for more information. Typically the SCL packages
will contain 'rh' in the name, but not all do.

How to use SCL packages
-----------------------

Once you have installed an SCL package you must first 'enable' its use and run
a program with the package enabled. For example::

   scl enable rh-python35 bash

This 'enables' the rh-python35 package (Python 3.5) and then runs the command
``bash``. The ``bash`` command is started with some environment variables
changed so that the SCL software is then available, in a similar way to how
:doc:`envmodules` work.

You can also enable two or more environments at the same time like so::

   scl enable sclone scltwo bash

In the above example both ``sclone`` and ``scltwo`` are enabled.

Using SCL without the ``scl`` command
-------------------------------------

Unlike the environment modules system the binaries of the programs do not have
a ``PREFIX`` set so they can locate shared libraries (shared/dynamic objects) 
without setting the ``LD_LIBRARY_PATH`` variable. This is set automatically by
the ``scl enable`` command. 

You can however source a script instead of having to use the ``scl`` command. 
Each SCL package is installed into ``opt``::

   /opt/rh/<package-name>/

Within that directory there is a script named ``enable`` which you can ``source``::

   source /opt/rh/<package-name>/enable

For example this is how to source Python 3.5::

   source /opt/rh/rh-python35/enable

