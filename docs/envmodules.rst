Environment modules system
==========================

Most of the scientific and research software provided by iSolutions uses the
environment modules system. Most if not all of the software on the IRIDIS 
super computer also uses the environment module system. 

The modules system is a way to dynamically alter your environment (e.g. 
variables in your terminal session) in a 'modular' way. An application 
specifies a 'module file' which contains code to modify the shell so that the
application works. You can then 'load' the module which uses the module file.

How to load a module
--------------------

First you have to install some software which makes use of the modules system,
for example you could install PyPy 5.6::

   sudo yum install pypy256

Once the package is installed you can switch into the module like so::

   module load pypy/5.6

Once loaded you can use the ``pypy`` binary directly.

How to unload a module
----------------------

Just replace ``module load`` with ``module unload``::

   module unload pypy/5.6

List available modules
----------------------

You can list all the modules installed with::

   module avail

Show the help for the module
----------------------------

Each module should have some help text, use this command to show it::

   module help pypy/5.6

List loaded modules
-------------------

You can list the modules in use right now type::

   module list
