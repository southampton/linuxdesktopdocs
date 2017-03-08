TeX Live (LaTeX)
================

TeX and LaTeX are document production tools otherwise known as typesetting 
systems. TeX and LaTeX are used to produce high quality documents and books, 
especially within academia. LaTeX is used for producing scientific documents
throughout the University.

TeX Live is a distribution which contains both TeX and LaTeX, among many other 
tools and programs.

Versions of TeX Live
--------------------

There are two versions of TeX Live available:

* Tex Live 2013: ``sudo yum install texlive``
* Tex Live 2016: ``sudo yum install texlive2016``

The former version is packaged by Red Hat and does not include the ``tlmgr`` 
TeX package manager. As such we recommend you install TeX Live 2016 which 
is the latest version and it includes the package manager.

Using Tex Live 2016
-------------------

TeX Live 2016 uses the :doc:`envmodules`. To use it open a terminal and 
run the following::

   module load texlive/2016

Once loaded you can use all the normal TeX/LaTeX commands (and man pages).

Installing TeX modules
----------------------

.. note::

   To install TeX modules via ``sudo tlmgr`` you need to be in the 
   Administrators group. See :doc:`permissions` for more information. You 
   can also install modules in your home directory if you prefer.

TeX Live 2016 comes with a package manager called ``tlmgr``. You can install
modules like so::

   sudo tlmgr install <modulename>

If you prefer to install a module just for yourself, or if you don't have 
permission to use ``sudo tlmgr``, run::

   tlmgr --usermode install <modulename>
