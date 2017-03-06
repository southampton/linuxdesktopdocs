Virtualisation
==============

VirtualBox
----------

iSolutions recommends the use of VirtualBox for creating and running virtual
machines on the linux desktop platform. VirtualBox is designed for a multi user
environment, unlike KVM/libvirt which runs everything as root. 

You can install the latest VirtualBox with the following command::

   sudo yum install VirtualBox-5.1

Older versions are available but we recommend you install the latest.

Once installed you can start VirtualBox and start creating virtual machines 
straight away! We recommend you store your virtual machine disks in the
``/local/scratch/<username/`` directory - see :doc:`storage` for more info.

Rebuilding the kernel module
----------------------------

After a ``kernel`` update is installed you might find that VirtualBox no longer
works and generates an error similar to ``Kernel driver not installed ``. To fix
this you must run the following command in a terminal::

   sudo /usr/lib/virtualbox/vboxdrv.sh setup

To run the above command you must be in the ``sys`` or ``vboxusers`` group. See
:doc:`permissions` for more information.

VirtualBox user group
---------------------

In previous versions of VirtualBox anybody who wanted to use the software had
to be in the ``vboxusers`` group. This is no longer the case and membership of
this group is only required if:

* You want to be able to rebuild the kernel module without being in ``sys``
* You want to be able to use USB passthrough devices 

See :doc:`permissions` for more information.
