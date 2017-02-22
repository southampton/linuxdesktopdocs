Installing software
===================

Desktop Manager
---------------

The recommended method for installing software is via the :doc:`deskctl` tool.
This tool contains specialist software, packages created by iSolutions, and
all software specifically requested by members of the university. If a package
is missing from it, and you think it should be listed, let us know!

GNOME Software
--------------

You can use the GNOME Software tool to install software. This too only contains
a subset of all software available, specifically it does not include specialist
software or packages created by iSolutions. It only includes graphical
applications, no terminal applications or specialist tools are included.

It does however include most of the default software in Red Hat Enterprise 
Linux so if you're looking for a standard GUI application then GNOME
Software will probably let you install it.

To start GNOME Software press the Start button and search for "Application 
Installer". 

The terminal
------------

If you're not afraid of the command line then the easiest and fastest way to 
install software is to use ``yum``. You can search for software like this:

  
   .. code-block:: shell
    
        sudo yum search <name>

You can then install a package once you've found it like this:

   .. code-block:: shell
    
        sudo yum install <package-name>

Or remove a package:

   .. code-block:: shell
    
        sudo yum remove <name>

