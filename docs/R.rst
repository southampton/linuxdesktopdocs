R
=

R is an open source programming language intended for use within statistical 
computing and data analysis. It is not installed by default on the Linux
desktop platform but it can be installed easily via the following command 
in a terminal::

   sudo yum install R

Installing R packages
---------------------

There are two methods to installing R packages. Either install them via ``yum``
or via ``CRAN`` within R itself. Only a limited number of packages are available
via yum so we recommend using R itself.

To find the list of R packages you can install via yum run this command::

   sudo yum list R-\*

Since very few packages are available its best to install packages via CRAN 
from within R. First start R in a terminal::

   R

then enter the following command::

   install.packages("pkgname")

Replace ``pkgname`` with the package to install, e.g. for Bio3D::

   install.packages("bio3D")

You can install multiple packages like this::

   install.packages(c("bio3D","devtools"))

The first time you try to install packages R will prompt you to install into
your home directory and create a library there, do so and you will be able to 
install R packages.

.. note::

   If you wish to install the ``devtools`` package you should first run the 
   command ``sudo yum install openssl-devel libcurl-devel libssh2-devel`` so
   that the prerequisite development files are available.

Sadly there is no easy way to allow via ``sudo`` the ability for you to install
R packages system wide so any user can use them. This is because you must first
start R as root and execute a specific command. We'll keep working on a way to 
solve this but as for now you'll need to install R packages in your home 
directory - sorry about that!
